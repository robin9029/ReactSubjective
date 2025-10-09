https://griddynamics.medium.com/front-end-security-best-practices-8c47d23caf62
https://medium.com/insiderengineering/in-depth-security-in-your-frontend-applications-6297c25d1f9c
https://medium.com/insiderengineering/in-depth-security-in-your-node-js-backend-applications-674740b7592e

# SBI CORPORATION
1. Cross-Site Scripting (XSS) attacks: 
2. Cross-Site Request Forgery (CSRF) attacks: 
3. Injection attacks: 
4. Security risks in external scripts:  
5. Broken access control:

## BEST Practice
1. Input validation and sanitization
2. Avoid inline scripts
3. Content Security Policy (CSP)
4. Secure HTTP requests
5. Penetration testing
6. Dependency management
   
## 1.Cross-Site Scripting (XSS) attacks : malicious code is injected
- Example (Unsafe HTML + JS)
```html
<!DOCTYPE html>
<html>
<head>
  <title>Unsafe Example</title>
</head>
<body>
  <h1 id="msg"></h1>

  <!-- Inline script (NOT SAFE) -->
  <script>
    // Let's say this comes from user input
    const userInput = "<img src=x onerror='alert(`XSS Attack!`)'>";
    document.getElementById("msg").innerHTML = userInput;
  </script>
</body>
</html>
```
### 🧩 Secure HTML + External JS Example set up **CSP 

#### `index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Secure Example</title>

  <!-- Add a strict CSP -->
  <meta
    http-equiv="Content-Security-Policy"
    content="default-src 'self'; script-src 'self'; style-src 'self';"
  />
</head>
<body>
  <h1 id="msg"></h1>

  <!-- Load external JS (trusted only from 'self') -->
  <script src="app.js"></script>
</body>
</html>
```

#### `app.js`

```javascript
// Safe JavaScript file
const msg = document.getElementById("msg");

// Simulated user input
const userInput = "<img src=x onerror='alert(`XSS`)'>";

// Instead of using innerHTML, use textContent to prevent HTML injection
msg.textContent = userInput;
```

✅ **Why this is safe:**

* No inline `<script>` tags.
* CSP blocks any untrusted scripts.
* `textContent` prevents malicious HTML execution.

## 🔒 React Example (Best Practice)

- React already protects against XSS by default because it **escapes** all values rendered inside JSX.
- JSX 🔹 React **renders** the input as plain text — not as HTML.
- So you’ll literally see `<img src=x onerror='alert("XSS")'>` on the screen, and **no script executes.**
- ⚠️ Only Use `dangerouslySetInnerHTML` When You’re 100% Sure
- Example with Sanitization

```jsx
import DOMPurify from "dompurify";

export default function App() {
  const userInput = "<img src=x onerror='alert(`XSS`)'>";

  return (
    <div
      dangerouslySetInnerHTML={{
        __html: DOMPurify.sanitize(userInput),
      }}
    />
  );
}
```

✅ Here, `DOMPurify.sanitize()` removes any malicious scripts before rendering.

## 2. Cross-Site Request Forgery (CSRF) attacks: 
- an attacker sends a link to a logged-in user that causes a bank transfer to be executed without their knowledge
#### 1️⃣ Victim is logged in to their bank site

```plaintext
https://mybank.com
```
The user has a valid login session, and the browser holds the **auth cookie**:
```
sessionid=abc123
```

#### 2️⃣ Attacker lures user to visit a malicious page

```plaintext
https://evilsite.com
```

#### 3️⃣ Evil site sends a hidden request to bank

```html
<!-- Inside evilsite.com -->
<html>
  <body>
    <h1>You won a prize! 🎁</h1>

    <!-- Hidden auto-submitting form -->
    <form action="https://mybank.com/transfer" method="POST">
      <input type="hidden" name="toAccount" value="attacker123">
      <input type="hidden" name="amount" value="5000">
    </form>

    <script>
      document.forms[0].submit(); // auto submit silently
    </script>
  </body>
</html>
```

👉 Since the victim is already logged in to **mybank.com**, the browser automatically includes their **cookies** (session ID).


### ✅ solution1:  CSRF Token (Recommended)

The **server generates a random token** that must be included in every form or AJAX request.
If the token is missing or invalid → the request is rejected.
* Server creates a random token (`req.csrfToken()`).
* Token is embedded in form (or sent with AJAX header).
* On POST, the server validates that token.
* An attacker cannot guess or read the token due to **same-origin policy**.

### ✅ solution2: Use `SameSite` Cookies

Modern browsers support `SameSite` attribute for cookies — which restricts cookies from being sent in cross-origin requests.

#### Example (in Express)

```javascript
app.use(
  cookieSession({
    name: "session",
    keys: ["secret"],
    cookie: {
      httpOnly: true,
      secure: true,
      sameSite: "Strict", // 🚫 stops cross-site requests
    },
  })
);
```

## 3) What is an injection attack (short)

An **injection attack** happens when untrusted input is incorporated into a command/query/HTML/JS that the application runs without proper treatment. Examples:

* **SQL injection** — attacker injects SQL fragments into database queries.
* **XSS (HTML/JS injection)** — attacker injects scripts into pages returned to users.
* **NoSQL injection** — attacker supplies crafted JSON/inputs that change MongoDB queries.
* **Command injection** — attacker controls arguments to shell/OS commands.

**Key point:** The server executes something containing attacker-controlled strings. Fixes must primarily be server-side (where commands/queries run). Frontend can help reduce risk and should follow safe patterns.

## 3.1) How the frontend can *enable* injection

Frontend mistakes that make injection easier:

* Sending unsanitized inputs that server blindly concatenates into SQL or shell commands.
* Rendering user-supplied HTML with `innerHTML` or `dangerouslySetInnerHTML` without sanitization (XSS).
* Passing raw JSON from form directly into a DB query-building endpoint that uses string interpolation or `eval`.
* Allowing complex structured inputs that the server `JSON.parse`s into selectors that get executed.

So the frontend’s role:

* **Never** trust user input — always validate on server.
* But also: **use safe rendering** and **limit what you accept** — defense in depth.
### A — Unsafe SQL usage (vulnerable server)

**Do not** do string concatenation with user input:

```js
// server.js (UNSAFE) — do NOT use
app.post('/search', express.json(), async (req, res) => {
  const { q } = req.body; // attacker controls q
  // DANGEROUS: string concatenation -> SQL INJECTION
  const sql = `SELECT * FROM users WHERE name LIKE '%${q}%'`;
  const { rows } = await db.query(sql); // if db.query executes raw SQL
  res.json(rows);
});
```

If `q` = `%' OR '1'='1` this could return all users or worse.

#### ✅ Safe version using parameterized queries (Postgres + `pg`)

```js
// server.js (SAFE)
import express from "express";
import pg from "pg";

const app = express();
app.use(express.json());

const pool = new pg.Pool({ connectionString: process.env.DATABASE_URL });

// Use parameterized queries — NEVER build SQL with string concat
app.post('/search', async (req, res) => {
  const { q } = req.body;
  // Use placeholders $1 and pass values separately
  const sql = "SELECT * FROM users WHERE name ILIKE $1";
  const { rows } = await pool.query(sql, [`%${q}%`]); // q is treated as data
  res.json(rows);
});
```

**Why safe:** DB driver sends the SQL and parameters separately. The DB engine treats the parameter as data, not executable SQL.



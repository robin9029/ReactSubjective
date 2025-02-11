# Nodejs Server Code (JWT Authentication)

```
const express = require("express");
const jwt = require("jsonwebtoken");
const bcrypt = require("bcryptjs");

const app = express();
app.use(express.json());
const SECRET_KEY = "your_secret_key";

```
- this is the kist of available login created
```
const users = [{ id: 1, username: "admin", password: bcrypt.hashSync("password", 8), role: "admin" }];
```


- Login Route -user login via this API-http://localhost:5000/login
```
  app.post("/login", (req, res) => {
  const { username, password } = req.body;
  const user = users.find(u => u.username === username);
  if (!user || !bcrypt.compareSync(password, user.password)) { 
    return res.status(401).json({ message: "Invalid credentials" });    // if fails return error 
  }  
 // Generate Token

  const token = jwt.sign({ userId: user.id, role: user.role }, SECRET_KEY, { expiresIn: "1h" });
  res.json({ token });
});

```
- Protected Route
```
app.get("/dashboard", verifyToken, (req, res) => {
  res.json({ message: `Welcome User ${req.user.userId}`, role: req.user.role });
});
```
- Middleware to Verify Token
```
function verifyToken(req, res, next) {
  const token = req.headers.authorization?.split(" ")[1];
  if (!token) return res.status(403).json({ message: "Access Denied" });

  jwt.verify(token, SECRET_KEY, (err, decoded) => {
    if (err) return res.status(403).json({ message: "Invalid Token" });
    req.user = decoded;
    next();
  });
}
```
# 2. Frontend (React)
```
import React, { useState } from "react";
import axios from "axios";

const Login = () => {
  const [username, setUsername] = useState("");
  const [password, setPassword] = useState("");
  const [token, setToken] = useState(localStorage.getItem("token") || "");

  const handleLogin = async () => {
    try {
      const response = await axios.post("http://localhost:5000/login", { username, password });
      localStorage.setItem("token", response.data.token);
      setToken(response.data.token);
    } catch (error) {
      console.error("Login failed", error.response.data.message);
    }
  };

  const fetchDashboard = async () => {
    try {
      const response = await axios.get("http://localhost:5000/dashboard", {
        headers: { Authorization: `Bearer ${token}` },
      });
      console.log(response.data);
    } catch (error) {
      console.error("Access denied", error.response.data.message);
    }
  };

  return (
    <div>
      <h2>Login</h2>
      <input type="text" placeholder="Username" onChange={(e) => setUsername(e.target.value)} />
      <input type="password" placeholder="Password" onChange={(e) => setPassword(e.target.value)} />
      <button onClick={handleLogin}>Login</button>
      <button onClick={fetchDashboard}>Access Dashboard</button>
    </div>
  );
};

export default Login;
```
app.listen(5000, () => console.log("Server running on port 5000"));

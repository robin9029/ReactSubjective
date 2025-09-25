
## ✅ Printable Interview Questions – 12+ Years Exp (FastAPI, PostgreSQL, React)

---

### 🧠 **System Design & Architecture (Full Stack Focus)**

1. **Design a scalable full-stack web application** using React (frontend), FastAPI (backend), and PostgreSQL (DB).

   * How would you structure the backend for scalability?
   * How would you separate concerns between API layers, services, and data access layers?

2. **How do you approach building a secure authentication system** using JWT and role-based access control?

   * How would you handle token refresh, CSRF, and XSS protection?
   * Where would you store tokens: cookies, localStorage, or elsewhere?

3. **What’s your strategy for database schema versioning and migrations** in PostgreSQL?

   * How do you use tools like Alembic or others in a CI/CD pipeline?

4. **How do you handle API versioning and backward compatibility** when the frontend is tightly coupled with the backend?

5. **Discuss your deployment strategy** for a full-stack app using Docker, Kubernetes, or cloud services.

   * What trade-offs do you consider when choosing container orchestration or PaaS?

---

### ⚙️ **Backend: FastAPI + PostgreSQL**

1. **How does FastAPI leverage Python type hints and Pydantic for validation and documentation?**

   * How would you customize validation or error handling globally?

2. **What’s your pattern for handling transactions and connection pooling** with PostgreSQL in FastAPI?

   * Tools: SQLAlchemy, asyncpg, or databases library?

3. **How do you optimize PostgreSQL queries** for performance in high-traffic environments?

   * Usage of indexes, query planning, denormalization?

4. **Describe how you handle long-running or asynchronous background tasks** in FastAPI.

   * Use of Celery, FastAPI’s `BackgroundTasks`, or external queues?

5. **How do you implement multi-tenancy or sharding in PostgreSQL**, and how would FastAPI interact with it?

6. **Describe how you secure FastAPI endpoints** with OAuth2 scopes or third-party identity providers (e.g., Auth0, Keycloak).

7. **How do you monitor and log your FastAPI application?**

   * Integration with tools like Prometheus, Grafana, ELK stack?

---

### ⚛️ **Frontend: React (Advanced)**

1. **How do you manage large-scale state across your React app?**

   * Compare and contrast Redux, Zustand, Jotai, Recoil, and React Query.

2. **How do you architect component libraries** or design systems for use across multiple projects?

   * How do you document them (Storybook, Styleguidist, etc.)?

3. **What is your approach to form validation and dynamic forms?**

   * Libraries: React Hook Form, Yup, Formik — which do you prefer and why?

4. **Describe your strategy for secure token management in React apps.**

   * How do you persist sessions securely without exposing JWTs to XSS?

5. **How do you ensure accessibility and performance in complex React UIs?**

   * Tools: Lighthouse, axe-core, useMemo optimizations, lazy loading?

6. **How do you handle real-time updates in React apps?**

   * WebSockets, Server-Sent Events, or polling — and which layer handles reconnection logic?

---

### 🔁 **Integration & DevOps**

1. **How do you orchestrate the CI/CD pipeline** for a FastAPI + React + PostgreSQL stack?

   * Tools: GitHub Actions, GitLab CI, CircleCI, Docker Compose?

2. **How would you handle CORS, reverse proxy, and static file serving** in a production-grade deployment?

3. **What is your approach to error boundary and logging** in both React and FastAPI?

4. **How do you handle schema drift between frontend and backend models (e.g., DTOs)?**

   * Any codegen or shared schema strategies?

5. **Explain how you do end-to-end testing across the stack.**

   * Do you use tools like Cypress (frontend), Pytest/TestClient (backend), and Postgres test containers?

---

## 📝 Format Tips (For Printing/Sharing)

* Use this in a **PDF or printed format** with headers like:

  * *Core Area: Backend | Frontend | DevOps*
  * *Level: Senior Architect*
  * *Skill Focus: Design Thinking | Performance | Security*

## BAckend


## 🧠 **Backend Layered Architecture — FastAPI + PostgreSQL**

We’ll use a clean, enterprise-level Python backend structure with separation of concerns across these layers:

| Layer                              | Responsibility                                     | Tools                      |
| ---------------------------------- | -------------------------------------------------- | -------------------------- |
| **API Layer**                      | Handles routing, HTTP requests, validation, auth   | FastAPI, Pydantic          |
| **Service Layer (Business Logic)** | Core app logic (e.g., job creation, access checks) | Python services            |
| **Repository / Data Access Layer** | DB transactions, queries, ORM logic                | SQLAlchemy, PostgreSQL     |
| **Database Layer**                 | Schema design, migrations, indexing                | PostgreSQL, Alembic        |
| **Background Task Layer**          | Asynchronous image generation                      | Celery, Redis, AI models   |
| **Utility Layer**                  | Logging, config, file storage, shared tools        | Python utils, boto3, etc.  |
| **Network Layer**                  | External communication (S3, auth providers)        | Requests, boto3, Auth libs |

---

## 📁 **Recommended Backend Folder Structure**

```
/app
├── api/                   # API routes (controllers)
│   └── generate.py
│   └── status.py
│   └── images.py
│
├── services/              # Business logic
│   └── image_service.py
│   └── user_service.py
│
├── repositories/          # Data access layer
│   └── image_repo.py
│   └── user_repo.py
│
├── models/                # SQLAlchemy models
│   └── image_job.py
│   └── user.py
│
├── schemas/               # Pydantic schemas
│   └── image.py
│   └── user.py
│
├── db/                    # DB session, base, Alembic config
│   └── session.py
│   └── base.py
│
├── tasks/                 # Celery tasks (background jobs)
│   └── worker.py
│   └── generate_image.py
│
├── utils/                 # Helpers, image I/O, S3 logic
│   └── storage.py
│   └── logger.py
│
├── core/                  # Config, startup, error handling
│   └── config.py
│   └── security.py
│   └── exceptions.py
```

---

## 🧩 Layer-by-Layer Breakdown with Examples

---

### 1. 🌐 **API Layer**

> Handles incoming HTTP requests, request validation, routing, auth

#### ✅ Example:

```python
# app/api/generate.py

@router.post("/generate")
def generate_image(request: ImagePromptRequest, db: Session = Depends(get_db), user: User = Depends(get_current_user)):
    job = image_service.create_image_job(request, user, db)
    tasks.queue_image_generation.delay(job.id)
    return {"job_id": job.id, "status": job.status}
```

---

### 2. ⚙️ **Service Layer (Business Logic)**

> Coordinates logic: permissions, validations, calls to repos & tasks

#### ✅ Example:

```python
# app/services/image_service.py

def create_image_job(request: ImagePromptRequest, user: User, db: Session):
    job = image_repo.create_job(db, user.id, request.prompt)
    return job
```

* Performs **business rules**:

  * Enforce prompt limits
  * Validate user quota
  * Trigger async task
  * Fetch image job result

---

### 3. 🗃️ **Repository / Data Access Layer**

> ORM and raw DB operations (CRUD), decoupled from logic

#### ✅ Example:

```python
# app/repositories/image_repo.py

def create_job(db: Session, user_id: int, prompt: str) -> ImageJob:
    job = ImageJob(user_id=user_id, prompt=prompt, status="QUEUED")
    db.add(job)
    db.commit()
    db.refresh(job)
    return job
```

* Uses SQLAlchemy for:

  * Queries
  * Joins
  * Pagination
  * Transactions

---

### 4. 🧱 **Database Layer**

> Schema, model definitions, migrations, indexes, constraints

#### ✅ SQLAlchemy Models:

```python
# app/models/image_job.py

class ImageJob(Base):
    __tablename__ = "image_jobs"

    id = Column(Integer, primary_key=True)
    user_id = Column(Integer, ForeignKey("users.id"))
    prompt = Column(String, nullable=False)
    status = Column(String, default="QUEUED")
    image_url = Column(String, nullable=True)
    created_at = Column(DateTime, default=datetime.utcnow)
```

#### ✅ Alembic Migrations:

```bash
alembic revision --autogenerate -m "Create image_jobs table"
alembic upgrade head
```

---

### 5. ⏱️ **Background Task Layer**

> Run long tasks outside the HTTP lifecycle (AI model call)

#### ✅ Celery Task:

```python
# app/tasks/generate_image.py

@celery_app.task
def queue_image_generation(job_id: int):
    job = image_repo.get_by_id(job_id)
    image_url = run_model_and_store_image(job.prompt)
    image_repo.update_status(job_id, "COMPLETED", image_url)
```

* Loads prompt
* Runs model (e.g., Stable Diffusion)
* Saves result to S3/local
* Updates job status

---

### 6. 🧰 **Utility Layer**

> Shared helper logic: image I/O, storage, logging, config

#### ✅ Example:

```python
# app/utils/storage.py

def save_image_to_s3(file_data: bytes, filename: str) -> str:
    s3 = boto3.client('s3')
    s3.upload_fileobj(BytesIO(file_data), BUCKET, filename)
    return f"https://cdn.example.com/{filename}"
```

* Could also include:

  * `logger.py`
  * `error_handler.py`
  * `validators.py`

---

### 7. 🌍 **Network Layer**

> Handles connections to external services (S3, OAuth, CDN)

* Auth provider integration (Auth0, Firebase, etc.)
* Upload/download from S3
* CDN delivery
* HTTPS headers / proxy setup

#### ✅ Example:

```python
# app/core/security.py

def decode_jwt_token(token: str) -> dict:
    return jwt.decode(token, SECRET_KEY, algorithms=["HS256"])
```

---

## 🔁 Data Flow (Backend Perspective)

```
1. [POST /generate]
    ↓
2. API Layer (validate + auth)
    ↓
3. Service Layer (create job)
    ↓
4. Repository Layer (DB insert)
    ↓
5. Celery Task (async model call)
    ↓
6. Image saved to S3
    ↓
7. DB updated with status + URL
    ↓
8. [GET /status/{job_id}] → returns image if ready
```

---

## ✅ Summary Table – Backend Layers (FastAPI + PostgreSQL)

| Layer                     | Folder            | Role                                 |
| ------------------------- | ----------------- | ------------------------------------ |
| **API Layer**             | `/api`            | Handle requests, validation, routing |
| **Service Layer**         | `/services`       | Business rules, orchestration        |
| **Repository Layer**      | `/repositories`   | DB interaction (CRUD, queries)       |
| **Database Layer**        | `/models`, `/db`  | Schema, migrations                   |
| **Background Task Layer** | `/tasks`          | Async image generation               |
| **Utility Layer**         | `/utils`, `/core` | Logging, config, file handling       |
| **Network Layer**         | `/utils`, `/core` | External services (S3, auth, CDN)    |

## Fronend


## 🧠 **Frontend Layered Architecture – Next.js 13+ (App Router)**

We’ll break it into layers:

| Layer                            | Responsibility                                | Tools                                   |
| -------------------------------- | --------------------------------------------- | --------------------------------------- |
| **Presentation Layer**           | UI components, forms, layouts                 | React + Next.js Components              |
| **Page (Routing) Layer**         | Navigation, SSR/ISR/CSR logic                 | Next.js App Router                      |
| **API Communication Layer**      | Fetching data from FastAPI backend            | Fetch API, Axios, React Query, SWR      |
| **State & Business Logic Layer** | State handling, job polling, token management | React Hooks, Context, Zustand           |
| **Utility Layer**                | Helpers, constants, types                     | TypeScript Utils                        |
| **Network Layer**                | Communication with backend / storage / CDN    | HTTPS, REST APIs, S3 URLs, Auth headers |

---

### 📁 **Recommended Folder Structure (Next.js App Router)**

```
/app                         → Next.js routing
  /page.tsx                  → Home page (prompt input)
/generate
  /page.tsx                  → Submit prompt (Form)
/status/[jobId]
  /page.tsx                  → Show generation status
/gallery
  /page.tsx                  → User history (paginated)
/api                         → Optional serverless backend (if needed)

📁 /components                → UI building blocks
  PromptForm.tsx
  ImageCard.tsx
  StatusLoader.tsx

📁 /hooks                    → Custom React hooks
  useGenerateImage.ts
  useJobStatus.ts
  useAuth.ts

📁 /lib                      → Utility logic
  apiClient.ts              → Axios/fetch wrapper
  getToken.ts               → Get JWT from storage
  constants.ts              → App-wide constants

📁 /context                  → Global state (if needed)
  AuthContext.tsx
  JobContext.tsx

📁 /types                    → TypeScript types
  image.ts
  user.ts
```

---

## 🧩 Layer-by-Layer Breakdown with Examples

---

### 1. 🎨 **Presentation Layer**

> Stateless components to display UI (reusable, pure UI)

#### ✅ Examples:

* `ImageCard.tsx`: Displays image + metadata
* `PromptForm.tsx`: Input form for prompt
* `StatusLoader.tsx`: Progress animation while waiting

#### 🔧 Example (PromptForm.tsx)

```tsx
export function PromptForm({ onSubmit }) {
  const [prompt, setPrompt] = useState("");

  return (
    <form onSubmit={onSubmit}>
      <input
        type="text"
        placeholder="Describe your image..."
        value={prompt}
        onChange={(e) => setPrompt(e.target.value)}
      />
      <button type="submit">Generate</button>
    </form>
  );
}
```

---

### 2. 🌐 **Page (Routing) Layer**

> Next.js routes for different views: generation, history, results.

#### ✅ Path Examples:

| Route             | Purpose                             |
| ----------------- | ----------------------------------- |
| `/`               | Home page / Prompt input            |
| `/generate`       | Submit prompt (uses form component) |
| `/status/[jobId]` | Show job status using polling       |
| `/gallery`        | Show user’s past generated images   |

#### 🔧 Example (app/status/[jobId]/page.tsx)

```tsx
export default function JobStatusPage({ params }) {
  const { data, isLoading } = useJobStatus(params.jobId);

  if (isLoading) return <StatusLoader />;

  return (
    <div>
      {data.status === 'COMPLETED' ? (
        <img src={data.image_url} />
      ) : (
        <p>Status: {data.status}</p>
      )}
    </div>
  );
}
```

---

### 3. 📡 **API Communication Layer**

> Handles requests to the FastAPI backend

#### ✅ Tools:

* `fetch`, `axios`
* React Query / SWR (for data caching, polling)
* Authorization headers (JWT bearer token)

#### 📁 `/lib/apiClient.ts`

```ts
export const apiClient = axios.create({
  baseURL: process.env.NEXT_PUBLIC_API_BASE,
  headers: {
    "Content-Type": "application/json",
  },
});
```

#### 📁 `/hooks/useJobStatus.ts`

```tsx
export function useJobStatus(jobId: string) {
  return useSWR(`/job-status/${jobId}`, fetcher, { refreshInterval: 2000 });
}
```

---

### 4. ⚙️ **State & Business Logic Layer**

> Global app state, shared data, auth management, polling

#### ✅ Tools:

* React Context API
* Zustand or Jotai (lightweight state)
* Local/session storage for token management

#### 📁 `/context/AuthContext.tsx`

```tsx
const AuthContext = createContext();

export function AuthProvider({ children }) {
  const [token, setToken] = useState(() => localStorage.getItem("token"));

  return (
    <AuthContext.Provider value={{ token, setToken }}>
      {children}
    </AuthContext.Provider>
  );
}
```

---

### 5. 🧰 **Utility Layer**

> Helper functions, config, constants, error formatters

#### ✅ Examples:

* `getToken()` – Get JWT from local storage
* `constants.ts` – e.g., API base URL
* `formatDate()` – format timestamps for UI

#### 📁 `/lib/getToken.ts`

```ts
export function getToken() {
  return localStorage.getItem("token");
}
```

---

### 6. 🌐 **Network Layer**

> Responsible for communication with external services

#### ✅ Examples:

* HTTPS REST API calls to FastAPI
* Fetching signed S3 URLs
* Auth headers
* Handling CORS, timeouts

#### 🔧 axios with auth header:

```ts
apiClient.interceptors.request.use((config) => {
  const token = getToken();
  if (token) {
    config.headers.Authorization = `Bearer ${token}`;
  }
  return config;
});
```

---

## 📦 Data Flow (Frontend Perspective)

```
[User Enters Prompt] 
     ↓
[PromptForm Component] → calls API via /lib/apiClient
     ↓
[FastAPI Creates Job] → Returns jobId
     ↓
[JobStatus Page] → uses /hooks/useJobStatus (polling)
     ↓
[Show Image or Error] → Render ImageCard
```

---

## ✅ Summary Table – Frontend Layers (Next.js)

| Layer                    | Folder                        | Description                       |
| ------------------------ | ----------------------------- | --------------------------------- |
| **Presentation Layer**   | `/components`                 | Stateless UI components           |
| **Page Layer**           | `/app/`                       | Routes, rendering views           |
| **API Layer**            | `/hooks`, `/lib/apiClient.ts` | Handles REST API communication    |
| **Business Logic Layer** | `/hooks`, `/context`          | Token mgmt, polling, global state |
| **Utility Layer**        | `/lib`, `/types`              | Helpers, constants, types         |
| **Network Layer**        | axios/fetch config            | Headers, tokens, CORS, retries    |

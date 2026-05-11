# 🎯 Smart Recruitment System
 
> A Full-Stack AI-Powered Recruitment Platform with Online Proctored Assessments
 
The **Smart Recruitment System** is a scalable full-stack hiring platform that automates recruitment workflows, candidate screening, and AI-powered online assessments with real-time proctoring.
 
It streamlines the complete hiring lifecycle — candidate applications to secure online testing and hiring pipeline management.
 
---
 
## 🚀 Key Highlights
 
- 🔐 JWT-based Authentication
- 🧠 AI-powered Online Proctoring
- 📊 Recruiter & Admin Dashboards
- 📝 Profile Management
- 🏗️ Modular Backend Architecture
- 🗄️ PostgreSQL Relational Database
- ☁️ Cloudinary Image Storage
- ⚡ Real-time Monitoring & Violations Tracking
 
---
 
# 🏗️ System Architecture
 
    Frontend (React + Vite)
            │
            ▼
    Backend API (NestJS)
            │
            ├── PostgreSQL (Database)
            ├── Cloudinary (Image Storage)
            └── FastAPI (AI Proctoring Service)
 
The system follows a modular service architecture, separating business logic and AI monitoring services for scalability and maintainability.
 
---
 
# ✨ Features
 
## 👩‍💼 Recruiter / Admin
 
- Create & manage job postings
- View applicants and resumes
- Schedule assessments
- Manage hiring pipeline stages
- Monitor test sessions
- Track candidate violations
- Filter candidates by experience bracket
 
## 👨‍💻 Candidate
- Take online proctored tests

 
## 🧠 AI Proctoring System
 
- Face detection & monitoring
- Tab switching detection
- Screenshot capture
- Real-time violation tracking
- Session-based monitoring
- Detection pause/resume handling
 
---
 
# 🛠️ Tech Stack
 
| Layer              | Technology |
|--------------------|------------|
| Frontend           | React + Vite |
| Backend API        | NestJS (Node.js) |
| Database           | PostgreSQL |
| ORM                | TypeORM |
| Authentication     | JWT |
| Proctoring Service | Python FastAPI |
| AI Model           | InsightFace |
| Image Storage      | Cloudinary |
 
---
 
# 📂 Project Structure
 
    Smart-Recruitment-System
    │
    ├── frontend/              # React (Vite) Client Application
    │
    ├── backend/
    │   ├── main-app/          # NestJS REST API
    │   └── proctoring-app/    # Python FastAPI AI Proctoring Service
    │
    └── README.md
 
---
 # ⚙️ Environment Configuration

The project uses environment variables for configuration.

A template file **`.env.example`** is already provided in the repository.

### Step 1 — Create your `.env` file

Copy the template and create your local environment file:

```bash
cp backend/main-app/.env.example backend/main-app/.env
```

### Step 2 — Update the values

Open the file:

```
backend/main-app/.env
```

Fill in your own values:

```
DB_HOST=localhost
DB_PORT=5432
DB_USERNAME=postgres
DB_PASSWORD=your_password
DB_NAME=db2025

JWT_SECRET_KEY=your_secret_key

CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=

FRONTEND_URL=http://localhost:5173
PORT=5000
```
 
# 🗄️ Database Setup (PostgreSQL)
 
1. Install PostgreSQL and pgAdmin.
2. Create a database 
3. Restore the provided database backup file.
4. Ensure PostgreSQL service is running.
5. Update `.env` credentials accordingly.
 
---

# 🐳 Docker Setup for Coding Platform

The coding platform executes user code inside Docker containers.  
So Docker Desktop must be installed and running before starting the project.

## Step 1 — Install Docker Desktop

Install Docker Desktop from:

https://www.docker.com/products/docker-desktop/

---

## Step 2 — Start Docker Desktop

Open Docker Desktop.

Docker Engine will automatically start and run in the background.

Make sure Docker is running before starting the coding platform.

---

## Step 3 — Pull Required Language Images

Run the following commands in your terminal (Git Bash / PowerShell / CMD):

| Language | Command |
|---|---|
| Python | `docker pull python:3.10` |
| Java | `docker pull openjdk:17` |
| JavaScript | `docker pull node:18` |
| C# | `docker pull mono:latest` |
| C++ | `docker pull gcc:13.2.0` |

---

## Step 4 — Docker Images Storage

After downloading, Docker automatically stores these images locally.

No additional configuration is required.

---

## Step 5 — Keep Docker Running

Docker Desktop must remain running while taking coding assessments or executing code from the editor.

---

# ⚠️ Important Instruction — Update Local Docker Volume Paths

The coding execution service uses local Docker volume mappings.

You must update the local paths inside:

```ts
src/utils/language-config.ts
```

---

## Step 1 — Locate the File

Open:

```ts
src/utils/language-config.ts
```

---

## Step 2 — Find `extraVolume` Entries

Locate entries containing paths like:

```ts
C:/Users/Sam Christopher/....
```

---

## Step 3 — Replace with Your Local System Paths

Update the paths with your own local folder paths.

### Instructions

1. Right-click the `Wrappers` folder

2. Click **Copy Path**

3. Replace single backslashes `\` with double slashes `//`

4. Repeat the same process for the `libs` folder

5. Save the file

---

## Example

```ts
"C://Users//sam christopher//Desktop//React-CodingPlatform//be-nest040925//src//utils//Wrappers"
```

```ts
"C://Users//sam christopher//Desktop//React-CodingPlatform//be-nest040925//src//utils//libs"
```

---

## Why This Is Required

Docker containers need access to:
- wrapper files
- language libraries
- execution utilities

Incorrect paths may cause:
- code execution failure
- missing file errors
- container runtime issues
 
# 🚀 Running the Project Locally
 
## 1️⃣ Clone Repository
 
    git clone https://github.com/SamChrstopher/smart-recruitment-system.git
    cd Smart-Recruitment-System
 
## 2️⃣ Start Backend (NestJS API)
 
    cd backend/main-app
    npm install
    npm run start:dev
 
Backend runs on:
 
    http://localhost:5000
 
## 3️⃣ Start Frontend (React + Vite)
 
Open a new terminal:
 
    cd frontend
    npm install
    npm run dev
 
Frontend runs on:
 
    http://localhost:5173
 
## 4️⃣ Start Proctoring Service (FastAPI)
 
Make sure Python 3.8+ is installed.
 
    cd backend/proctoring-app
    python -m venv venv
 
Activate Virtual Environment:
 
Windows:
    venv\Scripts\activate
 
macOS / Linux:
    source venv/bin/activate
 
Install dependencies:
 
    pip install -r requirements.txt
 
Run service:
 
    uvicorn app.main:app --reload
 
---
 
# 🌐 Access the Application
 
Open in your browser:
 
    http://localhost:5173
 
---
 
# 🧪 Available Scripts
 
## Backend
 
    npm run start:dev
    npm run build
    npm run start:prod
 
## Frontend
 
    npm run dev
    npm run build
    npm run preview
 
---
 
# 🔐 Security Considerations
 
- JWT-based authentication
- Secure environment variable management
- Role-based access control
- Cloudinary secure upload configuration
- Real-time proctoring violation logging
- Backend-first startup dependency
 
---
 
# 🛠️ Troubleshooting
 
## Backend Not Starting
 
    rm -rf node_modules
    npm install
 
Check:
- PostgreSQL is running
- `.env` credentials are correct
- Port 5000 is not occupied
 
## Database Connection Error
 
- Verify PostgreSQL service is active
- Confirm port (default: 5432)
- Check DB credentials in `.env`
 
## Python / Proctoring Errors
 
Recreate environment:
 
    python -m venv venv
    pip install -r requirements.txt
 
---
 
# 📈 Scalability & Design Approach
 
- Modular backend architecture
- Separate AI proctoring microservice
- Service-level isolation for monitoring
- Database-driven hiring pipeline
- Designed for horizontal scalability
 
---

 
# 📌 Important Notes
 
- Backend must run before frontend.
- Proctoring service must run for assessments.
- PostgreSQL must be active before backend starts.
- `.env` file must be configured correctly.
 
---

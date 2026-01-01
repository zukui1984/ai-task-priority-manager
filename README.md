# 📝 Task Priority Manager

## 📖 Problem Description
In a fast-paced environment, keeping track of daily tasks can be overwhelming. This **Task Priority Manager** solves this problem by providing a simple, visual interface to organize tasks. Users can create tasks, assign them a priority (**High**, **Medium**, **Low**), and track their completion status. The application ensures that critical tasks (Red/High) stand out, helping users focus on what matters most.

## 🚀 Features
- **Task Management:** Create, Read, Update, and Delete (CRUD) tasks.
- **Priority System:** Visual color coding (Red=High, Yellow=Medium, Green=Low).
- **Status Tracking:** Toggle tasks between "Pending" and "Completed".
- **Responsive UI:** Clean interface built with React.
- **Persistent Storage:** All data is saved in a PostgreSQL database.

## 🛠️ Tech Stack & Architecture
- **Frontend:** React (TypeScript) + Axios
- **Backend:** FastAPI (Python) + SQLAlchemy
- **Database:** PostgreSQL 15
- **Containerization:** Docker + Docker Compose
- **API Specification:** OpenAPI 3.1

### Project Structure
```text
project-root/
├── backend/            # FastAPI Application
│   ├── main.py         # Routes & Database Logic
│   ├── requirements.txt
│   └── Dockerfile
├── frontend/           # React Application
│   ├── src/            # Components (App.tsx)
│   ├── public/
│   ├── package.json
│   └── Dockerfile
├── docker-compose.yml  # Orchestration
├── openapi.yaml        # API Contract
├── AGENTS.md           # AI Workflow Documentation
└── README.md           # Project Documentation
```

### 🏃‍♂️ How to Run the Project
#### Prerequisites
- Docker & Docker Compose installed.

#### Steps 1 - Preparation:

1. Clone the repository:
```
git clone https://github.com/zukui1984/ai-task-priority-manager.git
cd project-root
```

2. Start the Application:
- Run the following command in the root folder:
```
docker-compose up --build
```

3. Access the App:
- Frontend (UI): http://localhost:3000
- Backend API Docs: http://localhost:8000/docs

### 🧪 Testing
The backend includes connection tests to ensure the database is reachable.
To run tests manually inside the container:
```
docker-compose exec backend pytest
```

### **Step 2: The AGENTS.md** 
*Create this file in your root folder `project-root/AGENTS.md`.*
```markdown
# 🤖 AI-Assisted Development

## 🛠️ Tools Used
- **GitHub Copilot / LLMs**: Used as the primary coding assistant for generating boilerplate code, debugging errors, and writing documentation.
- **Docker**: Used to containerize the full-stack application.

## 📝 Workflow & Prompts
I followed an iterative workflow where I acted as the "Architect" defining requirements, and the AI acted as the "Builder" implementing the code.

### 1. Planning & API Design
- **Prompt:** "Generate an OpenAPI 3.1 yaml specification for a Task Manager app. Include a Task schema with fields: id, title, description, priority (enum: low, medium, high), and completed (boolean)."
- **Outcome:** Created `openapi.yaml` first to serve as the contract between Frontend and Backend.

### 2. Backend Implementation
- **Prompt:** "Create a FastAPI app based on the openapi.yaml. Use SQLAlchemy for PostgreSQL. Handle CORS for localhost:3000."
- **Challenge:** Encountered `Connection Refused` errors when connecting to the database.
- **Fix Prompt:** "How to fix SQLAlchemy connection refused error when running FastAPI and Postgres in Docker Compose?" (Solution: Changed `localhost` to `db` service name).

### 3. Frontend Implementation
- **Prompt:** "Write a React App.tsx component that fetches tasks from /tasks. Display them in a list with different colors for priorities. Add a form to add new tasks."
- **Challenge:** Docker could not find `package.json`.
- **Fix Prompt:** "Fix npm error enoent package.json in Docker build." (Solution: Adjusted folder structure and Dockerfile COPY instruction).

### 4. Integration
- **Prompt:** "Write a docker-compose.yml to run FastAPI, React, and Postgres together. Ensure the backend waits for the database to be ready."
- **Outcome:** A seamless "one-command" startup using `docker-compose up`.

## 🚀 Conclusion
Using AI tools significantly speeded up the boilerplate coding (CRUD operations, Dockerfiles) allowing me to focus on architecture and debugging integration issues between containers.
````

### Step 3 - The OpenAPI Spec 
Ensure project-root/openapi.yaml exists.
```
openapi: 3.1.0
info:
  title: Task Priority Manager API
  version: 1.0.0
paths:
  /tasks:
    get:
      summary: List all tasks
      responses:
        '200':
          description: Successful response
    post:
      summary: Create a task
      responses:
        '201':
          description: Task created
  /tasks/{task_id}:
    delete:
      summary: Delete a task
      responses:
        '204':
          description: Task deleted
components:
  schemas:
    Task:
      type: object
      properties:
        title:
          type: string
        priority:
          type: string
          enum: [low, medium, high]
```

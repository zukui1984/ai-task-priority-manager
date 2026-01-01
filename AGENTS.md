# 🤖 AI-Assisted Development

## 🛠️ Tools Used
- **GitHub Copilot / ChatGPT**: Used as the primary coding assistant and debugger.
- **VS Code**: IDE environment.

## 📝 Workflow & Prompts
I followed an iterative "Architect-Builder" workflow where I defined the high-level requirements and the AI generated the implementation details.

### 1. Planning & Specification
- **Prompt:** "Generate an OpenAPI 3.1 yaml specification for a Task Manager app with CRUD operations and a Task schema including priority enum."
- **Outcome:** Created the `openapi.yaml` contract first to define the interface between Frontend and Backend.

### 2. Backend Development
- **Prompt:** "Write a FastAPI application in main.py that implements the openapi.yaml spec. Use SQLAlchemy for PostgreSQL and include CORS middleware."
- **Debugging Prompt:** "Fix SQLAlchemy connection refused error when connecting to postgres in Docker."
- **Outcome:** A functional FastAPI backend that correctly handles database connections via Docker networking.

### 3. Frontend Development
- **Prompt:** "Create a React component using Axios to fetch tasks from http://localhost:8000/tasks. Add a form to create tasks and display them with color-coded priority badges."
- **Debugging Prompt:** "Fix 'npm error enoent package.json' by correcting the Dockerfile COPY path."

### 4. Containerization (Docker)
- **Prompt:** "Write a docker-compose.yml file that links FastAPI, React, and PostgreSQL. Ensure the backend waits for the db to be ready."
- **Outcome:** A fully containerized application running with a single `docker-compose up --build` command.


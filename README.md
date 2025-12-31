# AI Task Priority Manager

## Structure 
```
project-root/
├── README.md
├── AGENTS.md (AI tools used)
├── openapi.yaml
├── backend/
│   ├── main.py
│   ├── models.py
│   ├── database.py
│   ├── Dockerfile
│   └── tests/
├── frontend/
│   ├── src/
│   ├── Dockerfile
│   └── package.json
├── docker-compose.yml
└── .github/workflows/ci-cd.yml
```

## Problem
People struggle to prioritize daily tasks. This app provides a simple web interface to manage tasks by priority (Low/Medium/High), mark completion, and view organized lists.

## Features
- Create tasks with title, description, priority
- List all tasks sorted by priority
- Update task priority/status
- Delete tasks
- Responsive React frontend + FastAPI backend + PostgreSQL

## Architecture
Frontend (React) → OpenAPI contract → Backend (FastAPI + SQLAlchemy + PostgreSQL) → Docker containers → GitHub Actions CI/CD

## Local Setup
1. `docker compose up`
2. Visit http://localhost

## Create AGENTS.md for AI Tools Documentation:

#### AI-Assisted Development

#### Tools Used
- **GitHub Copilot**: Generated 90% of code (FastAPI routes, React components, tests)
- **Prompts used**:
  - "Create FastAPI CRUD endpoints for Task model with title:str, desc:str, priority:enum(Low/Medium/High), completed:bool"
  - "React component to list tasks from /tasks API with priority colors"
  - "Pytest tests for FastAPI task endpoints"

## MCP Workflow
Used Cursor IDE with Copilot for agent-like code generation following OpenAPI spec.

### OpenAPI Specification
Create openapi.yaml using Copilot/ChatGPT. 
```
Prompt: "Create OpenAPI 3.1 spec for task manager with CRUD operations: POST /tasks, GET /tasks, PUT /tasks/{id}, DELETE /tasks/{id}. Task schema: id(int), title(str), description(str), priority(enum: 'low','medium','high'), completed(bool). Include responses 200/404."
```

# AI Task Priority Manager

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

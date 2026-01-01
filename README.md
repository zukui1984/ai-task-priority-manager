# 📝 Task Priority Manager

## 📖 Problem Description
Staying organized is difficult. This application solves that by providing a clean, prioritized task list. Users can add tasks, assign them a priority level (**High**, **Medium**, **Low**), and track their completion status. This helps users focus on what matters most.

## 🚀 Features
- **Create Tasks:** Add title, description, and priority.
- **Visual Priorities:** Tasks are color-coded (Red for High, Yellow for Medium).
- **Status Tracking:** Mark tasks as completed or pending.
- **Full Stack:** Built with modern technologies.

## 🛠️ Technologies
- **Frontend:** React + TypeScript (Bootstrapped with CRA)
- **Backend:** FastAPI (Python)
- **Database:** PostgreSQL
- **Containerization:** Docker & Docker Compose
- **API Spec:** OpenAPI 3.1

## 📂 Project Structure
```text
project-root/
├── backend/            # FastAPI Application
│   ├── main.py         # App entry point & Routes
│   ├── models.py       # Database models
│   └── Dockerfile
├── frontend/           # React Application
│   ├── src/            # Components & Logic
│   └── Dockerfile
├── docker-compose.yml  # Orchestration for DB, Backend, Frontend
├── openapi.yaml        # API Contract
└── AGENTS.md           # AI Tools Documentation
```

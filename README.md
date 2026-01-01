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

#### Steps:

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


***

### **Step 2: The AGENTS.md** - Put this code
*Create this file in your root folder `project-root/AGENTS.md`.*



## 🚀 Conclusion
Using AI tools significantly speeded up the boilerplate coding (CRUD operations, Dockerfiles) allowing me to focus on architecture and debugging integration issues between containers.

# 🤖 AI Multi-Agent Task & Schedule Manager

A full-stack multi-agent AI system built with **FastAPI**, **SQLite**, and **Vanilla JS**.

---

## 🏗️ Architecture

```
User Input
    │
    ▼
Primary Agent  ──(keyword NLP)──▶ Task Agent    ──▶ Task Tool    ──▶ SQLite
                                ▶ Calendar Agent ──▶ Calendar Tool ──▶ SQLite
                                ▶ Notes Agent    ──▶ Notes Tool    ──▶ SQLite
```

---

## 📁 Project Structure

```
Multi-Agent AI System/
├── backend/
│   ├── main.py                  ← FastAPI app entry point
│   ├── requirements.txt
│   ├── agents/
│   │   ├── primary_agent.py     ← Controller / router
│   │   ├── task_agent.py
│   │   ├── calendar_agent.py
│   │   └── notes_agent.py
│   ├── database/
│   │   ├── db.py                ← SQLite connection + init
│   │   └── models.py            ← Pydantic models
│   └── tools/
│       ├── task_tool.py
│       ├── calendar_tool.py
│       └── notes_tool.py
└── frontend/
    ├── index.html
    ├── style.css
    └── script.js
```

---

## 🚀 Quick Start

### 1. Install dependencies

```bash
cd backend
py -3.12 -m venv venv
venv\Scripts\activate
pip install --upgrade pip
pip install -r requirements.txt
```
### 2. Activate the Virtual Environment
```venv\Scripts\activate.bat```

### 3. Start the API server

```bash
uvicorn main:app --reload
```

The server starts at **http://127.0.0.1:8000**


## 🌐 API Endpoints

| Method | Endpoint           | Description              |
|--------|--------------------|--------------------------|
| POST   | `/process`         | Send a natural-language command |
| GET    | `/tasks`           | List all tasks           |
| GET    | `/events`          | List all events          |
| GET    | `/notes`           | List all notes           |
| DELETE | `/tasks/{id}`      | Delete a task            |
| DELETE | `/events/{id}`     | Delete an event          |
| DELETE | `/notes/{id}`      | Delete a note            |
| GET    | `/health`          | Health check             |
| GET    | `/docs`            | Swagger UI (auto-docs)   |

---

## 💬 Example Commands

| Input | Routes to |
|-------|-----------|
| `Add task to submit project tomorrow` | Task Agent |
| `Remind me to call the client Friday` | Task Agent |
| `Schedule team meeting at 3 PM` | Calendar Agent |
| `Book appointment tomorrow morning` | Calendar Agent |
| `Save note about AI multi-agent systems` | Notes Agent |
| `Remember to review quarterly report` | Notes Agent |

---

## 🛠️ Tech Stack

- **Backend**: Python 3.9+, FastAPI, Uvicorn
- **Database**: SQLite (zero setup)
- **NLP**: In-house keyword-based intent scoring (no external ML deps)
- **Frontend**: HTML5, CSS3-custom-properties, Vanilla JS (ES2022)

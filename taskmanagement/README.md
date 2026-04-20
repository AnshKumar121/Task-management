# 📋 TaskFlow — Task Management App

A full-stack Kanban-style task manager with a clean separation of **Frontend** (HTML/CSS/JS) and **Backend** (Node.js + Express + MongoDB).

---

## 📁 Project Structure

```
task-manager/
├── backend/
│   ├── server.js          # Express REST API
│   ├── package.json       # Node dependencies
│   └── sample-tasks.json  # Sample data for seeding
└── frontend/
    └── index.html         # Complete Kanban UI (HTML + CSS + JS)
```

---

## 🔧 Backend Setup

### Prerequisites
- Node.js v18+
- MongoDB running locally (`mongod`)

### Steps

```bash
cd backend
npm install
npm start         # or: npm run dev (uses nodemon for hot-reload)
```

Server runs at → `http://localhost:5000`

---

## 🎨 Frontend Setup

No build step needed. Just open the file in your browser:

```bash
# Option 1 — Open directly
open frontend/index.html

# Option 2 — Serve with VS Code Live Server extension
# Right-click index.html → Open with Live Server
```

> ⚠️ Make sure the backend is running before opening the frontend.

---

## 🔌 REST API Reference

| Method | Endpoint                     | Description           |
|--------|------------------------------|-----------------------|
| GET    | `/api/tasks`                 | Get all tasks         |
| GET    | `/api/tasks/:id`             | Get single task       |
| POST   | `/api/tasks`                 | Create new task       |
| PATCH  | `/api/tasks/:id`             | Update / move task    |
| DELETE | `/api/tasks/:id`             | Delete task           |
| GET    | `/api/tasks/status/:status`  | Filter by status      |

### POST /api/tasks — Request Body

```json
{
  "title": "Build the UI",
  "description": "Create the Kanban board layout",
  "status": "todo",
  "priority": "high",
  "dueDate": "2025-04-20"
}
```

---

## 🗄️ MongoDB Schema

```js
Task {
  title:       String (required)
  description: String
  status:      "todo" | "inprogress" | "done"
  priority:    "low" | "medium" | "high"
  dueDate:     Date
  createdAt:   Date (auto)
  updatedAt:   Date (auto)
}
```

---

## ✨ Features

- ✅ Create, edit, delete tasks
- 🔄 Move tasks between **To Do → In Progress → Done**
- 🖱 **Drag & Drop** between columns
- 🏷 Priority levels (High / Medium / Low) with color coding
- 📅 Due date support
- 📊 Live task counters per column
- 📱 Responsive layout

---

## 🛠 Tech Stack

| Layer    | Technology                        |
|----------|-----------------------------------|
| Frontend | HTML5, CSS3, Vanilla JavaScript   |
| Backend  | Node.js, Express.js               |
| Database | MongoDB + Mongoose ODM            |
| Data     | JSON (sample-tasks.json for seed) |

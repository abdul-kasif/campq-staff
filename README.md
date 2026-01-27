# CampQ Staff Portal

[![Frontend](https://img.shields.io/badge/Frontend-React%20%2B%20Vite-blue)](frontend/)
[![Backend](https://img.shields.io/badge/Backend-Ruby%20on%20Rails-red)](backend/)
[![Maintain](https://img.shields.io/badge/Maintain-Abdul%20Kasif-green)](https://github.com/abdul-kasif)

A secure staff portal system built with modern web technologies.

---

## Table of Contents

- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Clone & Setup](#clone--setup)
- [Running the App](#-running-the-app)
  - [Backend (Rails API)](#backend-rails-api)
  - [Frontend (React + Vite)](#frontend-react--vite)
- [Git Workflow](#-git-workflow)
- [Branching Rules](#-branching-rules)
- [Need Help?](#-need-help)
- [Pro Tips](#-pro-tips)

---

## Project Structure

```
campq-staff/
├── frontend/            → React + Vite UI
├── backend/             → Ruby on Rails API
├── README.md            → You are here!
└── .gitignore           → Ignored files (DO NOT MODIFY without approval from Abdul Kasif)
```

---

## Getting Started

### Prerequisites

- Node.js v18+ (for frontend)
- Ruby 3.0+ & Rails 7+ (for backend)
- PostgreSQL (or SQLite for development)
- Git

---

### Clone & Setup

```bash
# 1. Clone the repo
git clone https://github.com/abdul-kasif/campq-staff.git
cd campq-staff

# 2. Switch to develop branch (ALWAYS start from here!)
git checkout develop

# 3. Install dependencies

# For Frontend (React + Vite)
cd frontend
pnpm install

# For Backend (Rails)
cd ../backend
bundle install
rails db:setup  # or: rails db:create db:migrate
```

 **Note:** Never work directly on the `main` branch. Always use `develop` as your base.

---

## Running the App

### Backend (Rails API)

```bash
cd backend
rails s -p 3000
# ➜ API runs at: http://localhost:3000
```

Test with:

```bash
curl http://localhost:3000/api/health
# Expected: { "status": "ok" }
```

---

### Frontend (React + Vite)

```bash
cd frontend
pnpm run dev
# ➜ UI runs at: http://localhost:5173
```
---

## Git Workflow

follow a simplified Git Flow:

```
main          ← Production (Abdul only)
  ↑
develop       ← Integration branch (ALL work merged here)
  ↑     ↑     ↑
feature/*   feature/login-api   feature/dashboard   (your branches)
```

---

### Daily Steps

```bash
# 1. Get latest changes
git checkout develop
git pull origin develop

# 2. Create your feature branch
git checkout -b feature/your-task-name

# 3. Work → Commit often
git add .
git commit -m "feat: describe your work"

# 4. Push your branch
git push origin feature/your-task-name

# 5. Open PR on GitHub → Tag @abdul
#    Wait for review → I’ll test + merge into develop

# 6. After merge → clean up
git checkout develop
git pull
git branch -d feature/your-task-name
```

**Branch naming convention:**  
Examples → `feature/login-form`, `feature/api-user-profile`  
Be descriptive and specific.

---

## Branching Rules

| Branch    | Who          | Purpose                   |
|-----------|-------------|---------------------------|
| `main`    | Abdul only  | Production-ready code     |
| `develop` | PRs only    | Integration & testing     |
| `feature/*` | Everyone  | Individual task branches  |

**Protected Branches:** `main` and `develop` → No direct pushes. Always open a PR.

---

Built with care by **Abdul Kasif**  
Last updated: **January 2026**

# 🐳 Docker Setup Guide

## Project Structure

```
.
├── frontend/
│   └── Dockerfile
├── backend/
│   └── Dockerfile
├── docker-compose.yaml
└── docker.env.example
```

---

## Getting Started

### 1. Clone the Repository

After cloning the repo, run the following to fetch submodule files:

```bash
git submodule update --init
```

> ⚠️ Without this step, `frontend/` and `backend/` folders will be empty.

---

### 2. Setup Environment Variables


#### Backend
Copy the example config file and rename it:

```bash
cp backend/config/config.env.example backend/config/config.env
```

Then open `backend/config/config.env` and fill in your values.

#### Frontend
Copy the example env file and rename it:

```bash
cp frontend/example.env.local frontend/.env.local
```

Then open `frontend/.env.local` and fill in your values.

---

## Running the App

### 🛠️ Development

Starts the app with **live file watching** (auto-sync on file changes):

```bash
docker compose -f docker-compose-dev.yaml up --watch
```

### 🚀 Production

Starts the app in production mode:

```bash
docker compose -f docker-compose-prod.yaml up
```

---

## Notes

- Make sure [Docker](https://www.docker.com/) and [Docker Compose v2.22+](https://docs.docker.com/compose/) are installed
- Run `docker compose version` to verify your Compose version
- `--watch` requires the `develop.watch` config to be defined in your compose file
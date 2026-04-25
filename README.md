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

### 1. Setup Environment Variables

Copy the example env file and rename it:

```bash
cp docker.env.example docker.env
```

Then open `docker.env` and fill in your values:

```env
FE_DIR=./frontend
BE_DIR=./backend
# ... other variables
```

> ⚠️ Never commit `docker.env` to git — it contains sensitive values.

---

## Running the App

### 🛠️ Development

Starts the app with **live file watching** (auto-sync on file changes):

```bash
docker compose --env-file docker.env -f docker-compose-dev.yaml up --watch
```

### 🚀 Production

Starts the app in production mode:

```bash
docker compose --env-file docker.env -f docker-compose-prod.yaml up
```

---

## Notes

- Make sure [Docker](https://www.docker.com/) and [Docker Compose v2.22+](https://docs.docker.com/compose/) are installed
- Run `docker compose version` to verify your Compose version
- `--watch` requires the `develop.watch` config to be defined in your compose file
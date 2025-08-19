Shuffle Fullstack CI/CD Demo

This repository provides a containerized setup and CI pipeline for running Shuffle (open-source SOAR platform) with both its backend (Flask/Python) and frontend (React/Node).

The aim is to:

       Build Shuffle backend + frontend using Docker.

       Run them together via Docker Compose.

       Use GitHub Actions CI to verify services start correctly.

       Provide an easy way to clone and run Shuffle locally.

📂 Repository Structure

       .
├── .github/

│   └── workflows/

│  └── shuffle-docker.yml   # CI workflow for GitHub 
Actions 

├── Dockerfile.backend           # Dockerfile for Shuffle backend

├── Dockerfile.frontend          # Dockerfile for Shuffle frontend

├── docker-compose.yml           # Orchestrates backend + frontend

└── README.md                    # Project documentation




Components

Backend

       Python 3.11 + Flask API

       Runs Shuffle’s workflow engine and integrations

       Exposed on port 3001

Frontend

       React + Node.js build served by Nginx

       Provides Shuffle’s web UI

       Exposed on port 8080

GitHub Actions Workflow

       Builds backend & frontend Docker images

       Runs them with Docker Compose

       Performs health checks on API + UI

       Publishes logs if services fail

Run Locally

       1. Clone this repository
       git clone https://github.com/YOUR_githubfoam/shuffle-fullstack-ci.git
       cd shuffle-fullstack-ci

       2. Build and run with Docker Compose
       docker compose up --build

       3. Access services

       Backend API: http://localhost:3001

       Frontend UI: http://localhost:8080

       4. Stop containers

       docker compose down

Troubleshooting

Here are some common issues and fixes:

Frontend can’t reach backend

Make sure both services are up:

       docker compose ps

Confirm backend is running at http://localhost:3001.

Check container logs:

       docker compose logs backend

Frontend shows blank page

Ensure the frontend build completed successfully.

Rebuild containers:
       docker compose build --no-cache

Curl fails in CI (Shuffle not running)

Increase the wait time in workflow (sleep 30) before healthchecks.

View logs directly in CI run:

       - name: Show Logs
         run: docker compose logs backend


Port already in use

       Stop any process using port 3001 or 8080.

       Or change port mappings in docker-compose.yml.

Docker Compose command not found

       New versions use docker compose (space).

       If you have an older Docker, you may need docker-compose (hyphen).

GitHub Actions CI/CD

This repo includes a workflow (.github/workflows/shuffle-docker.yml) which:

       Runs on every push or pull_request to main.

       Builds Docker images for backend and frontend.

       Starts them with Docker Compose.

       Tests:

              curl http://localhost:3001 → backend healthcheck

              curl http://localhost:8080 → frontend healthcheck

       Cleans up containers after run.

You can see workflow runs under the Actions tab of your GitHub repo.

Requirements

       Docker

       Docker Compose

Optional (for development):

       Python 3.11

       Node.js 20+


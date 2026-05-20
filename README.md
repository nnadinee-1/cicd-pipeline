# CI/CD Pipeline with GitHub Actions & Docker

![CI/CD Pipeline](https://github.com/nnadinee-1/cicd-pipeline/actions/workflows/cicd.yml/badge.svg)

## Overview
Automated CI/CD pipeline that builds and pushes a Dockerized Flask app to Docker Hub on every push to `main`.

## Architecture
## Tech Stack
| Tool | Purpose |
|------|---------|
| Python Flask | Web application |
| Docker | Containerization |
| GitHub Actions | CI/CD automation |
| Docker Hub | Container registry |

## Project Structure
cicd-pipeline/
├── app/
│   ├── app.py              # Flask application
│   └── requirements.txt    # Python dependencies
├── .github/
│   └── workflows/
│       └── cicd.yml        # GitHub Actions pipeline
├── Dockerfile              # Container definition
├── .dockerignore           # Docker build exclusions
└── README.md
## Pipeline Steps
1. Triggered on every push to `main`
2. Checks out the code
3. Authenticates with Docker Hub using GitHub Secrets
4. Builds Docker image
5. Pushes image to Docker Hub

## Run Locally
```bash
docker pull nadineibrahim/cicd-pipeline:latest
docker run -p 5000:5000 nadineibrahim/cicd-pipeline:latest
curl http://localhost:5000
curl http://localhost:5000/health
```

## Endpoints
| Endpoint | Response |
|----------|---------|
| `/` | App status and version |
| `/health` | Health check |

## Key Concepts Demonstrated
- Secrets management (never hardcode credentials)
- Automated Docker builds
- Container registry integration
- Pipeline as Code

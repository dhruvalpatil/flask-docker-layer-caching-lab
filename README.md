# Flask Docker Layer Caching Lab

## Overview
A simple Python Flask application containerized using Docker. This project demonstrates Docker image creation, container execution, port mapping, and layer-cache optimization.

## Technologies
- Python
- Flask
- Docker
- Dockerfile
- Git and GitHub

## Run the application
```bash
docker build -f Dockerfile.v2 -t flask-cache-demo:v2 .
docker run -d --name flask-app -p 5000:5000 flask-cache-demo:v2
```

Open http://localhost:5000/

Health check: http://localhost:5000/health

## Layer caching experiment
- `Dockerfile.v1`: copies application files before installing dependencies.
- `Dockerfile.v2`: installs dependencies before copying application code.
- The optimized version can reuse the dependency layer when only application code changes.

## Learning outcomes
- Built and ran a Flask application inside Docker.
- Published container port 5000.
- Compared Dockerfile instruction ordering.
- Observed Docker layer-cache reuse.

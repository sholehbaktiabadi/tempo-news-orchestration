# Tempo News Project - Docker Compose Setup

## Overview
This repository contains the Docker Compose setup for the **Tempo News** project, which consists of the following services:
- **Backend**: A Node.js-based API service.
- **Frontend**: A React-based user interface.
- **PostgreSQL**: A relational database for storing data.
- **Redis**: A caching service to improve performance.

## Prerequisites
Make sure you have the following installed on your system:
- [Docker](https://www.docker.com/get-started)

## Getting Started
### 1. Clone the Repository
```sh
 git clone https://github.com/sholehbaktiabadi/tempo-news-orchestration.git
 cd tempo-news-orchestration
```

### 2. Create Environment Files
Ensure you have the required environment variable files before running the containers:
- `.env.backend` (for the backend service)
- `.env.frontend` (for the frontend service)

Place these files in the project root.

### 3. Pull frontend & backend image locally
Run the following command to pull images:
```sh
docker pull sholehbaktiabadi/tempo-news-api | docker pull sholehbaktiabadi/tempo-news-ui
```

### 3. Start the Containers
Run the following command to start all services:
```sh
docker compose up
```
This will start all services in detached mode.

### 4. Verify Running Services
Check the status of running containers:
```sh
docker ps
```

### 5. Access the Services
- **Frontend**: [http://localhost:4173](http://localhost:4173)
- **Backend**: [http://localhost:8000](http://localhost:8000)
- **PostgreSQL**: Connect using `localhost:5432` with credentials `postgres/root`
- **Redis**: Running on `localhost:6379`

## Data Persistence
- PostgreSQL data is stored in a Docker volume: `postgres_data`.

## Networking
All services are connected using the `app_network` bridge network.

## Dependencies
- **Backend** depends on PostgreSQL and Redis.
- **Frontend** depends on the Backend.



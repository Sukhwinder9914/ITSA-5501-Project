# ITSA-5501 Project – Milestone 2 (Docker Compose)

## Project Structure
- frontend/ (static website)
- docker/ (docker-compose.yml)
- prometheus.yml (Prometheus config)

## Services (Docker Compose)
- frontend (nginx:alpine) -> http://localhost:9090
- user-db (mongo) with volume user_data
- product-db (postgres) with volume product_data
- cache (redis)
- prometheus (prom/prometheus) -> http://localhost:9091

## Commands Used
### Start containers (detached)
docker-compose up -d

### View running containers
docker ps

### Scale frontend (Option B)
Added a second service `frontend-scale` (no host port mapping) and scaled it:
docker-compose up -d --scale frontend-scale=3
# NGINX Load Balancer for Flask Microservices

## Description

This project demonstrates how to build multiple Flask microservices and load balance them using NGINX as a reverse proxy. The entire setup is containerized using Docker and orchestrated with Docker Compose.

## Technologies Used

- Flask (Python Microservices)
- NGINX (Reverse Proxy & Load Balancer)
- Docker
- Docker Compose

## Architecture

- 2 independent Flask apps running on separate containers.
- NGINX container used as reverse proxy and load balancer.
- Docker Compose orchestrates all containers.

## Folder Structure

flask-nginx-loadbalancer/
├── app1/
│ └── app.py
├── app2/
│ └── app.py
├── nginx/
│ └── nginx.conf
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
└── README.md

markdown

Edit

## Setup

### Prerequisites

- Docker installed
- Docker Compose installed
- Basic knowledge of Docker commands

### Build & Run

Clone the repo and navigate into project folder.

```bash
docker-compose up --build
The application will be accessible at:

arduino

Edit
http://localhost:8080/
Refresh the page multiple times to observe load balancing between App 1 and App 2.

Docker Compose Details
app1 and app2 are separate Flask services built using Dockerfile.

nginx service uses official NGINX image.

NGINX routes incoming traffic to available Flask services.

Health Checks and Restart Policy
(Optional steps can be added to docker-compose.yml for health checks and auto restart)

Example:

yaml

Edit
healthcheck:
  test: ["CMD", "curl", "-f", "http://localhost:5000/"]
  interval: 30s
  retries: 3
restart: always
Clean Up
To stop and remove containers:

```bash

Edit
docker-compose down

Author
Supriya S P

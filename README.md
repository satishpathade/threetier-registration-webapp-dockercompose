# Three-Tier Registration Web App (Dockerized)

This project is a containerized three-tier web application where users submit a registration form and the data is stored in a MySQL database.  
The stack uses Nginx, PHP-FPM, and MySQL connected through Docker Compose networks.

---
## Architecture

- **Web Layer:** Nginx  
- **App Layer:** PHP-FPM  
- **Database Layer:** MySQL  
- **Containerization:** Docker + Docker Compose  
- **Persistent Storage:** Docker Volume  
- **Networking:** Custom Docker bridge networks  

## Features
- User registration form
- Data stored in MySQL
- Containerized 3-tier architecture
- Persistent database volume
- Inter-container communication via Docker networks
- Deployable on local machine or AWS EC2

---

## Key Concepts Used
- Docker Compose multi-container setup  
- Three-tier architecture  
- Nginx ↔ PHP-FPM configuration  
- MySQL container initialization  
- Docker volumes for persistence  
- Docker networks for service communication  

---

## Project Structure

```
Threetier-Registration-webapp
    ├── docker-compose.yml
    ├── README.md
    ├── app
    │ └── code
    │ └── submit.php
    ├── web
    │ ├── code
    │ │ └── signup.html
    │ └── config
    │ └── default.conf
    ├── db
    │ ├── Dockerfile
    │ └── init.sql
    └── Architecture
    └── architecture.png
```
## How to Run

### Prerequisites
1. launch ec2 and SSH 
    port 80 - allow

2. Docker installed
    `apt install docker -y `

3. Docker Compose installed

4. Clone the project repository
    `git clone <repo-url>`

5. Run container
    `docker compose up -d`

## Access the Application
    http://ec2-public-ip/signup.html

---

## Docker Services
| Service | Image | Purpose |
|--------|------|---------|
| web | nginx | Serves frontend |
| app | bitnami/php-fpm | Processes PHP |
| db | mysql | Stores data |


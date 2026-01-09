                  Capstone CI/CD Docker Web Application
A. Project Overview

This project demonstrates a complete CI/CD-enabled two-tier web application using Docker and Docker Compose.
It consists of a frontend served by Nginx, a backend API built using Flask, and a PostgreSQL database.

The project follows industry best practices such as:

* Multi-stage Docker builds
* Non-root containers
* Environment-based configuration
* Container orchestration using Docker Compose
* CI pipeline using GitHub Actions


B. Architecture Diagram

The application follows a simple layered architecture:

Browser → Frontend (Nginx) → Backend (Flask) → Database (PostgreSQL)

All services run inside Docker containers connected via a custom Docker network.


C. Technologies Used

* Docker & Docker Compose
* Python (Flask)
* Nginx
* PostgreSQL
* GitHub Actions (CI/CD)
* WSL2 (Linux environment)

D. Project Structure

capstone/
├── backend/
│   ├── Dockerfile
│   ├── app.py
│   └── requirements.txt
├── frontend/
│   ├── Dockerfile
│   ├── index.html
│   ├── style.css
│   └── app.js
├── db/
├── docker-compose.yml
├── diagrams/
└── README.md



E. How to Run the Application

E.1 Prerequisites

* Docker Desktop
* Docker Compose
* Git (optional)

E.2 Steps to Run

docker compose up --build


F. Application Access URLs

Frontend: [http://localhost:8080](http://localhost:8080)
Backend API: [http://localhost:5000](http://localhost:5000)


G. Docker & Containerization Details

* Backend uses a multi-stage Docker build to reduce image size
* Frontend runs on Nginx with a non-root user
* PostgreSQL data is persisted using Docker volumes
* Containers communicate through a Docker bridge network


H. CI/CD Pipeline

 GitHub Actions workflow is configured to:

* Trigger on push to the `main` branch
* Build frontend and backend Docker images
* Validate the `docker-compose.yml` configuration


I. Conclusion

This project successfully demonstrates Docker-based web application deployment with CI/CD integration, following modern DevOps and containerization best practices.


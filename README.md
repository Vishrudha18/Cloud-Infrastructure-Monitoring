# Infrastructure Automation & Real-Time Monitoring Platform

## Project Overview

This project demonstrates a complete DevOps workflow using AWS, Jenkins, Docker, GitHub, and Linux.

The platform automates application deployment through a CI/CD pipeline and hosts the application inside Docker containers running on AWS EC2.

---

## Architecture Diagram

```text
Developer
    │
    ▼
GitHub Repository
    │
    ▼
Jenkins Pipeline
    │
    ├── Clone Repository
    ├── Build Docker Image
    └── Deploy Container
    │
    ▼
Docker Container
    │
    ▼
AWS EC2 Instance
    │
    ▼
Web Application
```
---

## Features

- Source Code Management using GitHub
- Continuous Integration using Jenkins
- Automated Docker Image Build
- Automated Container Deployment
- AWS EC2 Hosting
- Linux Server Administration
- End-to-End CI/CD Pipeline

---

## Technology Stack

### Cloud
- AWS EC2

### DevOps Tools
- Jenkins
- Docker
- Git
- GitHub

### Operating System
- Ubuntu Linux

### Frontend
- HTML5
- CSS3

---

## CI/CD Workflow

1. Developer pushes code to GitHub.
2. Jenkins pulls the latest code.
3. Jenkins builds a Docker image.
4. Existing container is removed.
5. New container is deployed automatically.
6. Application becomes available through the EC2 public IP.

---

## Jenkins Pipeline

```groovy
pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-portfolio .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop devops-container || true
                docker rm devops-container || true
                docker run -d --name devops-container -p 80:80 devops-portfolio
                '''
            }
        }
    }
}
```

## Docker Configuration

```dockerfile
FROM nginx:latest

COPY . /usr/share/nginx/html

EXPOSE 80
```

## Project Structure

```
Cloud-Infrastructure-Monitoring/
│
├── index.html
├── style.css
├── Dockerfile
├── Jenkinsfile
└── README.md
```

---

## Deployment

Application is deployed on:

- AWS EC2
- Docker Container
- Jenkins Automated Pipeline

---

## Project Screenshots

### Jenkins Dashboard

![Jenkins Dashboard](screenshots/Jenkins%20Dashboard.png)

### Successful Jenkins Build

![Successful Build](screenshots/Successful%20Jenkins%20Build.png)

### Docker Container Running

![Docker Container](screenshots/Docker%20Container%20Running%20(docker%20ps).png)

### AWS EC2 Console

![AWS EC2](screenshots/AWS%20EC2%20Console.png)

### Project Website

![Website](screenshots/Project%20Website.png)

## Learning Outcomes

- CI/CD Pipeline Creation
- Docker Containerization
- Cloud Deployment
- Jenkins Automation
- Linux Administration
- GitHub Integration

---

## Future Enhancements

- GitHub Webhooks
- Prometheus Monitoring
- Grafana Dashboards
- Terraform Infrastructure Automation
- Docker Hub Integration
- Kubernetes Deployment

---

## Author

Vishrudha 

Information Technology Engineer | DevOps & Cloud Enthusiast
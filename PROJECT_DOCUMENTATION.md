Azure DevOps 3-Tier Application – Project Documentation
1️⃣ Project Overview

This project demonstrates the implementation of a Continuous Integration (CI) pipeline using Azure DevOps for a containerized three-tier web application.

The primary objective of this project was to automate the build process and validate application integrity using DevOps best practices.

2️⃣ Application Architecture
High-Level Architecture
                    End User
                        │
                        ▼
               Frontend Service (Nginx)
                        │
                        ▼
                Backend API (Node.js)
                        │
                        ▼
                   MongoDB Database
--------------------------------------------------------
Containerized using Docker
CI managed by Azure DevOps
Source Code hosted on GitHub
3️⃣ CI Pipeline Flow
        Developer
            │
            │  Push Code
            ▼
        GitHub Repository
            │
            │  Webhook Trigger
            ▼
     Azure DevOps CI Pipeline
            │
     ┌──────┴────────┐
     │               │
 Build Backend   Build Frontend
 Docker Image    Docker Image
     │               │
     └──────┬────────┘
            │
      Build Validation
            │
            ▼
   Build Successful / Logs Generated
4️⃣ Tech Stack

Node.js

Express.js

Nginx

Docker

GitHub

Azure DevOps

5️⃣ Project Structure
azure-devops-3tier-app/
│
├── backend/
│   ├── app.js
│   ├── package.json
│   └── Dockerfile
│
├── frontend/
│   ├── index.html
│   └── Dockerfile
│
└── azure-pipelines.yml
6️⃣ CI Implementation Details

GitHub is configured as the source repository.

Azure DevOps pipeline is triggered automatically on every push to the main branch.

Separate Docker images are built for frontend and backend services.

Build logs are generated for validation and troubleshooting.

The pipeline ensures application build consistency across environments.

7️⃣ Software Development Lifecycle (SDLC) Implementation
Requirement Phase

The requirement was to implement CI automation for a Dockerized multi-tier application.

Development Phase

Application components were developed independently:

Backend API service

Frontend static service

Build Phase

Dockerfiles were created to containerize both services.

Integration Phase

Azure DevOps pipeline was integrated with the GitHub repository using webhooks.

Testing Phase

Build validation was performed during pipeline execution to ensure successful container image creation.

Deployment Phase

Deployment to Azure Kubernetes Service (AKS) is planned as a future enhancement.

8️⃣ Future Enhancements

Push Docker images to Azure Container Registry (ACR)

Implement Continuous Deployment (CD)

Deploy application to Azure Kubernetes Service (AKS)

Add monitoring using Azure Monitor

Implement integration testing stage

Configure rollback strategy

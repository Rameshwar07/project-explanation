# 💼 Project Overview

Client: Vyapar  
Domain: Finance (Enterprise Resource Planning - ERP)  
Application Name: Vyapar ERP  
Domain Name: vyaparapp.in  
Team Size: 17 Members  
2 Frontend Developers (FD)  
4 Backend Developers (BD)  
2 Full-stack Developers (FD)  
3 Testers (T)  
2 DevOps Engineers (DE)  
1 Project Manager (PM)  
2 Cloud Engineers (CE)  
1 Security Engineer (SE)  

## 🧩 Technology Stack

Frontend: React (3 micro frontends)  
Backend: Spring Boot with Maven (31 microservices)  
Database: MongoDB  
Architecture: Microservices  
Infrastructure: Hybrid Cloud using:
AWS S3 (for static assets, backups)  
Amazon EKS (Elastic Kubernetes Service – managed Kubernetes)  
MongoDB Atlas or self-hosted (NoSQL database)  

## 🔧 Microservices Breakdown

### Frontend Microservices:
marketing – public landing pages  
admin – admin dashboard
user – user dashboard  

### Backend JARs/Services (Spring Boot):
Billing.jar – handles invoice generation, GST  
Inventory.jar – manages stock  
Cart.jar – handles shopping cart  
Employee.jar – HR module  
Auth.jar – login, JWT, OAuth  
User, Dashboard, Report, Barcode – other core services  
Each microservice is containerized, versioned, and deployed independently using CI/CD.

## ☁️ Infrastructure

#### Hybrid Cloud: 
Combination of on-prem and AWS cloud.  
#### S3 Buckets:
 Used for storing reports, logs, backups, user uploads.  
#### EKS: 
All microservices run as Docker containers on Kubernetes clusters managed by EKS.  
#### MongoDB:
Stores transactional and user data (used as a NoSQL database).  

## 🔀 Branching Strategy

Your team followed a multi-environment Git branching model:

DEV → TEST → QA → STAGING → UAT → PREPROD → PROD  
DEV: Developers push initial code.  
TEST: Unit tests and component testing.  
QA: Manual and automated testing by QA team.  
STAGING: Production-like environment for integration.  
UAT: Client-side user acceptance testing.  
PREPROD: Last check before PROD.  
PROD: Final production deployment.  
release: Used to tag release versions and rollback easily.  

As a DevOps engineer, you were involved in configuring the CI/CD pipelines for each environment.

## 🚀 DevOps Role in Detail

You handled CI/CD using pipelines with the following stages:

## 🛠️ Pipeline Stages

### PULL
Source code pulled from GitHub/GitLab/Bitbucket (depending on SCM).  
Triggered via webhooks or manually.

### BUILD
Compiles the Java code using Maven.  
Generates .jar files for each backend service.  
Runs unit tests during the build.  

### DOCKER-BUILD
Builds Docker images for each microservice (Dockerfile present in each repo).  
Tags image with version and pushes to Docker registry (ECR or DockerHub).  

### Q-TEST
Deploys Docker containers to a test namespace on EKS.  
Runs automated integration and quality tests (maybe via Postman, Newman, or JMeter).  

### DEPLOY
Deploys the image to the desired environment (QA, STAGING, PROD) using Helm or kubectl.  
Kubernetes manifests or Helm charts define the deployment, services, configMaps, secrets, etc.  

## 📌 Your DevOps Responsibilities
As a DevOps Engineer with 2 years of experience, your main contributions were:

### 🔹 CI/CD
Created and maintained pipelines (Jenkins/GitLab CI/AWS CodePipeline).  
Integrated Maven, Docker, and Kubernetes into pipelines.  
Used Helm charts or raw Kubernetes manifests for deployment.  

### 🔹 Docker & Kubernetes
Dockerized backend services (Dockerfile for each .jar).  
Wrote Kubernetes YAMLs or Helm charts for deployment.  
Managed pods, services, ConfigMaps, secrets, ingress controllers (ALB/Nginx), and autoscaling.

### 🔹 Monitoring & Logging
Integrated tools like Prometheus and Grafana for monitoring.  
Used ELK or CloudWatch for centralized logging.  

### 🔹 Cloud & S3
Created and managed S3 buckets for static file storage and backups.  
Set up policies, versioning, and lifecycle rules on S3.  

### 🔹 Access Control
Managed IAM roles for EC2, EKS, S3 access.  
Implemented RBAC in Kubernetes.  

## ✨ How to Explain in Interview (Example Answer)
"I worked on the Vyapar ERP project in the finance domain, which was built using a microservices architecture on a hybrid cloud infrastructure. Our backend had over 30 Spring Boot services deployed on EKS as Docker containers. I was responsible for managing CI/CD pipelines with stages like pull, build, docker-build, quality-test, and deploy. I used Docker and Kubernetes extensively, created Helm charts for each service, and automated deployments across environments like DEV, QA, and PROD. I also managed S3 buckets for file storage and helped monitor the infrastructure using Prometheus and Grafana. The branching strategy followed was multi-stage from DEV to PROD, ensuring safe code promotion through environments."
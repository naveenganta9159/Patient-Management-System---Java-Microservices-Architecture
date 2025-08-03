# 🏥 Patient Management System - Java Microservices Architecture

This is a production-grade backend system for managing patients in a healthcare setup,
built using **Java**, **Spring Boot**, and **Microservices**. 
It integrates advanced features like gRPC, Kafka, Docker, JWT Authentication, API Gateway, Integration Testing, and AWS Cloud Deployment with IaC.
---

## 📚 Project Overview

This system simulates a real-world healthcare backend and includes:

- Patient CRUD operations
- Billing service using gRPC
- Kafka-based analytics
- API Gateway with route filtering
- JWT-based Authentication with centralized Auth Service
- Docker-based microservices
- Integration testing
- Infrastructure as Code (AWS CloudFormation)

---

## 🧰 Tech Stack

| Layer                   | Technology                               |
|------------------------|-------------------------------------------|
| Language               | Java 17                                   |
| Framework              | Spring Boot, Spring Cloud                 |
| Microservices Toolkit  | Spring Cloud Gateway, Eureka, Config      |
| Security               | Spring Security, JWT                      |
| Messaging              | Apache Kafka                              |
| Remote Procedure Call  | gRPC                                      |
| API Testing            | Postman, Swagger (OpenAPI)                |
| Database               | MySQL                                     |
| Communication          | OpenFeign, RestTemplate                   |
| Containerization       | Docker, Docker Compose                    |
| Monitoring             | Sleuth, Zipkin (optional)                 |
| Testing                | Integration Testing, JUnit                |
| CI/CD & Deployment     | AWS EC2, LocalStack, AWS CLI, CloudFormation |

---

## 🧱 Microservices Breakdown

### 1. **Patient Service**
- REST CRUD operations
- Data validation and exception handling
- Integration with gRPC (Billing) and Kafka (Analytics)

### 2. **Billing Service**
- gRPC-based billing calculation
- Dockerized microservice with protocol buffers

### 3. **Analytics Service**
- Kafka consumer for patient events
- Event-driven analytics handling

### 4. **Auth Service**
- Login, Signup
- JWT-based authentication
- Integration with API Gateway for auth validation

### 5. **API Gateway**
- Filters, request validation, token passing
- Centralized entry point for frontend/client

### 6. **Config Server & Eureka Discovery**
- Central configuration for all microservices
- Service discovery using Spring Cloud Eureka

---

## ⚙️ How to Run the Project

### ✅ Prerequisites

- Java 17+
- Maven
- Docker & Docker Compose
- MySQL or Dockerized MySQL
- AWS CLI + LocalStack (for cloud simulation)

---

### 🚀 Run Microservices Locally

# In each service directory:
mvn spring-boot:run

# Run with Docker Compose
docker-compose up --build
Make sure docker-compose.yml includes services like:
MySQL
Kafka
Zookeeper
Auth Service
Patient Service
Billing Service
Analytics Service
API Gateway

---
# JWT Authentication Flow
POST /auth/signup — Register user
POST /auth/login — Login and receive JWT
Use JWT in header:
Authorization: Bearer <your-token>

---

#  📊 Kafka Event Flow
PatientService → Sends event after patient is created
AnalyticsService → Kafka consumer listens to events
Real-time logs or metrics can be updated
---
#  📡 gRPC Flow
PatientService → Calls BillingService via gRPC
BillingService → Returns billing info per patient

---

#  🧪 Integration Testing (JUnit)
Login endpoint test
Unauthenticated access test
Get Patient endpoint test
Test coverage for secured endpoints

---

#  ☁️ AWS Deployment (IaC)
Setup
Install AWS CLI
Configure LocalStack or AWS credentials
Infrastructure
CloudFormation templates: VPC, ECS, MSK, DB, Load Balancer
Auto-deploy with Docker images

---

#  🧑‍💻 Author
Mahesh Konda
📍 Oklahoma, USA
📫 maheshkreddy64@example.com

---
#  Acknowledgements
Special thanks to @JavaGuides for the end-to-end system tutorial.
All architectural decisions and implementations are aligned with modern cloud-native backend systems.

---

#  📄 License
This project is licensed under the MIT License.
```bash

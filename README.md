# 🌱 Automated Greenhouse Management System 

A **microservices-based system** designed to monitor and automate greenhouse operations, enabling efficient control of environmental conditions and crop management.

---

## 🚀 Execution Order (CRITICAL)

To start the system correctly, follow this sequence:

### 🔹 Phase 1: Infrastructure
> ⚠️ Start each service and wait until it is fully running before proceeding.

- **Config Server** *(Port: 8888)*  
  Centralized configuration provider for all services.

- **Eureka Server** *(Port: 8761)*  
  Service registry for microservices.  
  👉 Verify: http://localhost:8761

- **API Gateway** *(Port: 8080)*  
  Main entry point for all incoming requests.

---

### 🔹 Phase 2: Domain Services

- **Identity Service**  
  Handles authentication and JWT-based security.

- **Zone Management Service**  
  Manages greenhouse zones and structural data.

- **Crop Management Service**  
  Tracks crop data and lifecycle information.

- **Sensor Telemetry Service**  
  Processes real-time environmental data.

- **Automation Control Service**  
  Controls devices and logs automation actions.

---

## ⚙️ Configuration Repository

The AGMS system uses an external centralized configuration repository:

🔗 https://github.com/Hirusha-silva/agms_config.git

## 🛠 Prerequisites

Ensure the following tools are installed:

- Java 21+
- MySQL 8.x
- Maven
- Git

---

### 📌 Overview

This repository acts as the **central configuration source** for all microservices using **Spring Cloud Config Server**.

It provides environment-specific configurations (`application.yml`, service-specific configs) that are dynamically loaded at runtime.

### ✅ Key Features

- Centralized configuration management
- Environment-based configurations (dev, prod)
- No need to rebuild services after config changes
- Organized and maintainable configuration structure

> ⚠️ Ensure this repository is properly linked in the **Config Server (`application.yml`)** before starting the system.

---

## 📡 Gateway Routes

All services are accessible via the API Gateway:

| Service        | Endpoint              |
|---------------|----------------------|
| Identity      | `/api/v1/auth/**`    |
| Zones         | `/api/v1/zones/**`   |
| Crops         | `/api/v1/crops/**`   |
| Telemetry     | `/api/v1/telemetry/**` |
| Automation    | `/api/v1/automation/**` |

---

## 💡 Notes

- Start infrastructure services before domain services
- Ensure MySQL is running before launching services
- Confirm services are registered in Eureka
- Use Postman or similar tools to test APIs through the gateway

---
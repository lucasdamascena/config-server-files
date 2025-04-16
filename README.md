
# 📁 config-server-files

This repository contains configuration files used by Spring applications via Spring Cloud Config Server.

## 🛠️ Purpose

The `config-server-files` repository serves as a **remote configuration source**. It is consumed by a Spring Cloud Config Server application, which in turn provides these centralized configurations to various microservices or applications.

## 📄 Structure

- `application.yml` and `application-{profile}.yml` files
- Support for multiple profiles (e.g., `dev`, `prod`, etc.)
- Centralized and version-controlled configuration management
- Easy to update configurations without restarting services (via `/actuator/refresh`)

## 🔗 Example Usage

An application like `greeting-service` fetches its configuration from the Config Server, which points to this repository.

```bash
GET http://localhost:8080?name=YourName
```

If any changes are made to the files in this repository, the service can refresh its configuration using:

```bash
POST http://localhost:8080/actuator/refresh
```

## 🚀 How to Use

1. Start the Config Server and configure it to point to this Git repository.
2. Ensure the configuration files are properly structured and named.
3. Start the services that rely on the Config Server.
4. Check the application logs to verify the configuration was loaded correctly.

---

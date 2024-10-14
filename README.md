# Spring Boot Security Actuator

This project demonstrates how to integrate Spring Boot's Actuator with Spring Security to monitor and manage application metrics securely.

## Features

- **Spring Boot Actuator** for monitoring application health, metrics, and system information.
- **Spring Security** for securing sensitive endpoints exposed by the Actuator.
- Role-based access control to protect Actuator endpoints.

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/ertugrulgaripardic/spring-boot-security-actuator.git


Security Configuration
The project includes basic security configuration to restrict access to sensitive endpoints like /actuator and its sub-paths. You can configure user roles and permissions in the application.properties file or create custom security settings as needed.

Endpoints
/actuator/health - Check the application's health status.
/actuator/metrics - View application performance metrics.
Technologies Used
Spring Boot
Spring Security
Spring Boot Actuator
Maven

# Spring Boot Security Actuator

This project demonstrates how to seamlessly integrate Spring Boot Actuator with Spring Security to monitor and manage critical application metrics and system health securely. By combining Actuator's monitoring capabilities with Spring Security's robust access control mechanisms, sensitive endpoints are safeguarded, ensuring only authorized users can access system insights.

## Features:
Spring Boot Actuator: Provides endpoints for monitoring application health, system metrics, and runtime environment details.
Spring Security Integration: Secures sensitive Actuator endpoints to prevent unauthorized access

Role-Based Access Control: Grants fine-grained access based on user roles (e.g., ADMIN, USER)
Custom Endpoint Protection: Enables security customization for specific Actuator endpoints as needed
Health Monitoring: Offers real-time application health checks through /actuator/health
Metrics Tracking: Provides insights into JVM memory, garbage collection, and other performance-related data.

Flexible Configuration: Configure user roles and permissions dynamically via application.properties or custom security settings.sefsfg

Ease of Integration: Maven-based project structure ensures quick setup and dependency management.

# Prerequisites

To run and test this project successfully, ensure the following dependencies are installed

Java 17+

Maven 3.8+

Spring Boot 3.x

Spring Security

How to Run

Clone the repository

git clone https://github.com/ertugrulgaripardic/spring-boot-security-actuator.git

Navigate to the project directory:

cd spring-boot-security-actuator

Build the project using Maven:

mvn clean install

Run the application:

mvn spring-boot:run

Access the Actuator endpoints at:

Health Check: http://localhost:8080/actuator/health

Metrics: http://localhost:8080/actuator/metrics

Login credentials (configured in application.properties):

Username: admin

Password: password

Role: ADMIN

Note: Update credentials as needed based on your security requirements.

Security Configuration

The project includes a basic yet flexible security configuration to restrict access to sensitive Actuator endpoints. Spring Security ensures that only authenticated and authorized users can access these endpoints:

/actuator: Root endpoint for all Actuator-related functionality.

/actuator/health: Publicly accessible endpoint (can be customized).

/actuator/metrics: Secured with role-based access control (requires ADMIN role).

The security settings can be found in the SecurityConfig.java file, where endpoints are protected based on user roles. You can:

Customize access rules (e.g., allowing specific roles to access certain endpoints).

Secure additional Actuator paths dynamically.

Modify authentication settings as required.

Example configuration in application.properties:

# Basic authentication credentials
spring.security.user.name=admin
spring.security.user.password=password
spring.security.user.roles=ADMIN

# Enable all Actuator endpoints
management.endpoints.web.exposure.include=*
management.endpoint.health.show-details=always

Actuator Endpoints

Below are some of the key Actuator endpoints provided by this project:

Health

URL: /actuator/health

Purpose: Displays the application's current health status.

Example Output:

{
  "status": "UP",
  "components": {
    "db": { "status": "UP" },
    "diskSpace": { "status": "UP" }
  }
}

Metrics

URL: /actuator/metrics

Purpose: Provides performance and runtime metrics (e.g., JVM memory, CPU usage, garbage collection).

Example Output (partial):

{
  "names": [
    "jvm.memory.used",
    "jvm.gc.pause",
    "system.cpu.usage"
  ]
}

Environment

URL: /actuator/env

Purpose: Displays application environment properties.

Logs

URL: /actuator/loggers

Purpose: Allows viewing and updating log levels dynamically.

Tip: Expose or secure additional endpoints as required by modifying application.properties.

Technologies Used

Spring Boot: Simplifies application setup and configuration.

Spring Security: Ensures endpoint security with role-based access control.

Spring Boot Actuator: Provides health monitoring and system metrics.

Maven: For dependency management and build automation.

Java 17: Core programming language for the project.

Customization

You can customize the following aspects of the project:

Security Settings: Update roles, permissions, or add JWT-based security for enhanced protection.

Actuator Endpoints: Expose or restrict additional endpoints as needed.

Health Indicators: Add custom health indicators to monitor specific components.

Metrics: Extend Actuator's metrics functionality for custom application-specific monitoring.

Why Use This Project?

Secure Monitoring: Protects sensitive operational data using Spring Security.

Centralized Insights: Gain real-time visibility into application health and performance.

Scalability: Extendable to meet complex enterprise monitoring needs.

Developer-Friendly: Quick and easy integration with minimal configuration.

Conclusion

This project demonstrates an effective approach to securing Spring Boot Actuator endpoints using Spring Security. By leveraging role-based access control and customizable configurations, it ensures robust monitoring without compromising security. Ideal for developers who need secure access to critical application health and performance metrics.

For more details and contributions, feel free to explore the GitHub repository.


# Book Store Microservices App

Welcome to my **Book Store Microservices** project! This is a fully functional Book Store application built with a **microservices architecture** using **Spring Boot** and **Docker**. Each microservice handles specific business functionalities like managing the catalog, processing orders, and sending notifications. The project emphasizes modularity, scalability, and maintainability.

## App Workflow
![Screenshot 2024-09-23 182743](https://github.com/user-attachments/assets/4aaac190-04c9-4d92-bc70-f077e5b9aaee)

## Project Structure

This project follows a **multi-module** setup with separate microservices for each feature of the Book Store:

- **Catalog Service**: Manages book details (CRUD operations)
- **Order Service**: Manages customer orders and transactions
- **Notification Service**: Sends email notifications
- **API Gateway**: Routes external requests to the appropriate services
- **Bookstore WebApp**: Frontend service for user interaction

Each service is built independently and can be scaled or deployed separately, making it a perfect example of a microservices architecture.

## Technologies and Tools

Here are the key technologies and tools I used in the project:

- **Spring Boot**: Core framework for building microservices.
- **Spring Cloud Gateway**: For routing requests and handling cross-cutting concerns like authentication.
- **Spring Data JPA**: For interacting with the database.
- **Docker**: All microservices are containerized for consistent and scalable deployments.
- **Spring Security with JWT**: For authentication and authorization.
- **RabbitMQ**: For messaging and asynchronous communication between services.
- **Feign Client**: For declarative REST client, simplifying inter-service communication.
- **PostgreSQL**: Can be integrated as the primary database.

## Architecture and Design Patterns

### Microservices Architecture
This project follows a **microservices architecture**, breaking down the application into smaller, independent services. Each service is responsible for one piece of business functionality and can be deployed, updated, or scaled independently.

### API Gateway Pattern
I used **Spring Cloud Gateway** to implement the API Gateway. It serves as the entry point for all client requests and routes them to the correct microservices.

### Event-Driven Architecture
The services communicate asynchronously using **RabbitMQ** as the message broker. For example, when an order is placed, an event is sent to the **Notification Service** to send a confirmation message to the customer.

### Inter-Service Communication
I used **Feign Client** to simplify inter-service communication between the microservices. It abstracts away much of the boilerplate needed to make REST calls between services.

### Authentication and Authorization
The system is secured using **JWT tokens** for authentication, and **Spring Security** manages access control, ensuring that only authorized users can perform specific actions.

### Docker for Containerization
Each microservice is dockerized, which means they run in isolated containers. This allows for consistent environments across development, staging, and production.

### CI/CD Pipeline (GitHub Actions)
I have implemented continuous integration and deployment using **GitHub Actions**, which automatically builds and tests the services, and can deploy them using Docker images.

## Microservices Overview

1. **Catalog Service**:
   - Handles CRUD operations for books and categories.
   - Uses **Spring Data JPA** for database interactions.
   - The database used is **H2** for development/testing, but can be switched to **MySQL/PostgreSQL**.

2. **Order Service**:
   - Processes customer orders, including payment handling.
   - Uses **RabbitMQ** for communication with the notification service.
   - Implements transactional behavior to ensure order consistency.

3. **Notification Service**:
   - Sends email or SMS notifications to customers once an order is placed.
   - Communicates with other services via **RabbitMQ** or REST API calls.

4. **API Gateway**:
   - Provides a single entry point for all services.
   - Uses **Spring Cloud Gateway** for routing and load balancing.

5. **Bookstore WebApp**:
   - Acts as the frontend for users to browse, add to cart, and make purchases.
   - Built using **Thymeleaf** and integrates with the backend services via REST APIs.

## How to Run

### Prerequisites
- **Java 17**
- **Maven**
- **Docker**

### Steps to Run Using Docker
1. Clone the repository:
   ```bash
   git clone https://github.com/KOMPALALOKESH/Book-store-Microservices.git
   cd Book-store-Microservices
   ```
2. Build and run all services using Docker Compose:
   ```bash
   git clone https://github.com/KOMPALALOKESH/Book-store-Microservices.git
   cd Book-store-Microservices
   ```
   ```bash
   copy code..
   docker-compose up --build
   ```
3. Access the services:<br>
  API Gateway: ```http://localhost:8080``` <br>
  Catalog Service: ```http://localhost:8081```<br>
  Order Service: ```http://localhost:8082```<br>
  Notification Service: ```http://localhost:8083```<br>
  WebApp: ```http://localhost:8084```

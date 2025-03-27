# spring-boot-hexagon-arch
# Spring Hexagonal Architecture Template

## 📌 Introduction
This project is a Spring Boot template following the **Hexagonal Architecture** (Ports & Adapters pattern). It provides a clean and modular structure to separate business logic from external dependencies.

## 🏗️ Project Structure
```
spring-hexagonal-template/
│── applications/
│   ├── app-rest/           # REST API application
│   ├── app-cli/            # CLI application
│── adapters/
│   ├── in/
│   │   ├── rest/           # REST controllers
│   │   ├── cli/            # CLI adapters
│   ├── out/
│   │   ├── persistence/    # Database access layer
│   │   ├── messaging/      # Kafka, RabbitMQ, etc.
│   │   ├── external-api/   # External API integrations
│── domain/
│   ├── model/              # Business entities
│   ├── services/           # Business logic
│── config/                 # Application configurations
│── docs/                   # Project documentation
│── pom.xml                 # Maven dependencies
│── README.md               # Documentation
```

## 🚀 Technologies Used
- **Spring Boot** - Core framework
- **Spring Data JPA** - Database interaction
- **Spring Web** - REST APIs
- **Spring Security** - Authentication & Authorization
- **MapStruct** - Object mapping
- **Testcontainers** - Integration testing
- **Lombok** - Reduce boilerplate code
- **Docker** - Containerization

## 🛠️ Getting Started
### Prerequisites
- Java 17+
- Maven 3+
- Docker (optional, for running services)

### Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/spring-hexagonal-template.git
   cd spring-hexagonal-template
   ```
2. Build the project:
   ```sh
   mvn clean install
   ```
3. Run the application:
   ```sh
   mvn spring-boot:run
   ```

## 🏗️ Architectural Overview
This project follows **Hexagonal Architecture**, also known as the **Ports and Adapters** pattern. It ensures that the business logic is independent of external frameworks or technologies.

### Hexagonal Architecture Explained
Hexagonal Architecture promotes a **clear separation of concerns** by defining three main layers:

1. **Domain Layer (Core Business Logic)**
   - This layer contains **business entities** and **business rules**.
   - It is **independent of external technologies** (e.g., databases, REST APIs, messaging systems).
   - Services in this layer define the core use cases of the application.

2. **Application Layer (Use Cases & Services)**
   - This layer acts as a **bridge between the domain and the outside world**.
   - It orchestrates the business logic and **interacts with inbound and outbound adapters**.
   - It defines **input and output ports** (interfaces) to decouple business logic from infrastructure.

3. **Adapters Layer (Ports & Adapters)**
   - **Inbound Adapters**: Expose functionalities via REST API, CLI, or other UI interactions.
   - **Outbound Adapters**: Connect to external systems like databases, messaging systems, or third-party APIs.
   - These adapters **implement the ports** defined in the Application Layer to provide specific implementations.

### Layers in Detail
| Layer              | Responsibilities                                              | Examples        |
|-------------------|--------------------------------------------------------|----------------|
| **Domain Layer**   | Core business logic, entities, value objects, domain services | `Order`, `UserService` |
| **Application Layer** | Defines use cases, coordinates domain logic with adapters | `OrderService`, `UserUseCase` |
| **Adapters Layer** | Handles external interactions (DB, APIs, UI, Messaging) | `OrderRepository`, `KafkaProducer` |

### Benefits of Hexagonal Architecture
✅ **Decoupling**: Business logic is independent of frameworks and databases.  
✅ **Flexibility**: Easily switch external systems (e.g., change database from MySQL to PostgreSQL).  
✅ **Testability**: Core business logic can be unit-tested without dependencies.  
✅ **Maintainability**: Clear separation of concerns makes the codebase easier to manage.  

## 🔗 Contributing
Feel free to open issues or submit pull requests!

Happy coding! 🚀

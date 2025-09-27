# Explore Singapore Auth Service

A robust, secure authentication service built with Spring Boot, Java, and PostgreSQL for the Explore Singapore platform.

## 🚀 Features

- **User Registration & Login**: Email/password authentication (planned)
- **Email Verification**: Secure email verification system (planned)
- **JWT Authentication**: Access and refresh token management (planned)
- **Rate Limiting**: Protection against brute force attacks (planned)
- **Input Validation**: Comprehensive request validation with Spring Boot Validation
- **Security Hardening**: Spring Security configuration
- **Error Handling**: Centralized error handling with logging (planned)
- **Database Integration**: PostgreSQL with Spring Data JPA (planned)
- **Testing**: Unit tests with JUnit 5 and Spring Boot Test
- **Java**: Type safety with Java and Spring Boot framework

## 🛠 Quick Start

## 🐳 Running with Docker Compose

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/)

### Start the Application

1. Build and start the services:

   ```powershell
   docker-compose up --build
   ```

   This will start both the PostgreSQL database and the Spring Boot application. The app will be available at [http://localhost:8080](http://localhost:8080).

2. To stop the services:

   ```powershell
   docker-compose down
   ```

3. To monitor logs:

   ```powershell
   docker-compose logs -f
   ```

### Development inside Docker

- To enable live code reload or interactive development, you can mount your source code as a volume in the `app` service in `docker-compose.yml` (see comments in the file for guidance).
- For debugging, expose additional ports as needed.

---

## 🛠 Quick Start (Local Development)

1. **Prerequisites:**

   - Java 17 or higher
   - Maven 3.6+
   - PostgreSQL (if not using Docker Compose)

2. **Build the project:**
   ```bash
   mvn clean compile
   ```
3. **Run the application:**
   ```bash
   mvn spring-boot:run
   ```
4. **Test the application:**
   ```bash
   curl http://localhost:8080/hello
   ```

## 📚 API Endpoints

### Currently Available:

- `GET /hello` - Simple hello world endpoint for testing

### Planned:

- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/verify-email` - Email verification
- `GET /api/auth/me` - Get user profile
- `POST /api/auth/refresh-token` - Refresh JWT token
- `GET /actuator/health` - Spring Boot health check

## 🏗 Architecture

Following Spring Boot best practices and layered architecture:

```
src/
├── main/
│   ├── java/com/exploresg/authservice/
│   │   ├── config/          # Configuration classes
│   │   ├── controller/      # REST controllers
│   │   ├── service/         # Business logic services (planned)
│   │   ├── repository/      # Data access repositories (planned)
│   │   ├── entity/          # JPA entities (planned)
│   │   ├── dto/             # Data transfer objects (planned)
│   │   ├── security/        # Security configuration (planned)
│   │   └── AuthServiceApplication.java
│   └── resources/
│       ├── application.properties
│       └── static/ & templates/
└── test/
    └── java/                # Unit and integration tests
```

## 🔐 Security Features (Planned)

- Password encoding with BCrypt
- JWT access & refresh tokens
- Method-level security with Spring Security
- Input validation with Bean Validation (JSR-303)
- CORS configuration
- Security headers configuration

## 🧪 Current Status

**Completed:**

- ✅ Spring Boot project setup
- ✅ Maven configuration with required dependencies
- ✅ Basic REST controller (`HelloWorldController`)
- ✅ Spring Security (temporarily disabled for development)
- ✅ Project structure following Spring Boot conventions

**In Progress:**

- 🔄 Database configuration and JPA setup
- 🔄 User entity and registration functionality
- 🔄 JWT authentication implementation

**Next Steps:**

- 📋 Implement user registration (UC-001)
- 📋 Database integration with PostgreSQL
- 📋 Email verification system
- 📋 Complete authentication flow

See UC-001.md for detailed use case documentation.

## 🔧 Development

**Build and test:**

```bash
# Compile the project
mvn clean compile

# Run tests
mvn test

# Package the application
mvn clean package

# Run with Maven
mvn spring-boot:run

# Run the JAR file
java -jar target/exploresg-auth-service-0.0.1-SNAPSHOT.jar
```

**Environment Configuration:**

- Default port: 8080
- Profile: development (default)
- Security: Disabled for development phase

# Soft Scanner Project

A full-stack application for product management with logging and observability features, built with Spring Boot, React, MongoDB, and OpenTelemetry.

## Project Structure

```
soft-scanner/
├── docker-compose.yml
├── soft-scanner-web/     # Spring Boot backend
├── soft-scanner-frontend/ # React frontend
└── README.md
```

## Prerequisites

- Git
- Docker and Docker Compose
- Node.js (for local development)
- Java 17 (for local development)

## Installation Steps

1. Clone the main repository:
   ```bash
   git clone https://github.com/Neoxs/soft-scanner.git
   cd soft-scanner
   ```

2. Initialize and update the submodules:
   ```bash
   git submodule init
   git submodule update
   ```
   Or clone with submodules in one command:
   ```bash
   git clone --recurse-submodules https://github.com/Neoxs/soft-scanner.git
   ```

3. Build the backend (Spring Boot):
   ```bash
   cd soft-scanner-web
   ./mvnw clean package -DskipTests
   cd ..
   ```

4. Start all services using Docker Compose:
   ```bash
   docker-compose up --build
   ```

## Accessing the Applications

After successful startup, you can access:
* Frontend: http://localhost:80
* Backend API: http://localhost:8080
* MongoDB Express: http://localhost:8081
* Zipkin (tracing): http://localhost:9411

## Services

* **Frontend**: React application for user interface
* **Backend**: Spring Boot REST API
* **MongoDB**: Database for storing products and users
* **MongoDB Express**: Web-based MongoDB admin interface
* **Zipkin**: Distributed tracing system

## Environment Variables

MongoDB credentials (configured in docker-compose.yml):
```
Username: rootuser
Password: rootpass
```

## Troubleshooting

If you encounter issues:
1. Make sure all required ports are available:
   * 80 (Frontend)
   * 8080 (Backend)
   * 27017 (MongoDB)
   * 8081 (Mongo Express)
   * 9411 (Zipkin)

2. If containers don't start properly:
   ```bash
   # Stop all containers
   docker-compose down

   # Remove all containers and volumes
   docker-compose down -v

   # Rebuild and start
   docker-compose up --build
   ```

## Development

For local development:

1. Backend:
   ```bash
   cd soft-scanner-web
   ./mvnw spring-boot:run
   ```

2. Frontend:
   ```bash
   cd soft-scanner-frontend
   npm install
   npm run dev
   ```
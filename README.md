`````# SAIC Payment Microservices

This repository contains the payment microservices developed for SAIC to process secure and reliable transactions. The system is built with Java and Spring Boot, leveraging gRPC for inter-service communication, Resilience4j for resiliency patterns (circuit breaker, retries, rate limiting), and containerized with Docker and orchestrated via Kubernetes.

## Tech Stack

- **Language:** Java 17
- **Frameworks:** Spring Boot, Spring Cloud
- **Communication:** gRPC
- **Resiliency:** Resilience4j (circuit breaker, retries, bulkhead)
- **Containerization:** Docker, Kubernetes
- **Build Tool:** Maven

## Architecture

The solution follows a microservices architecture with separated services for payment initiation, processing, and reporting. Services communicate over gRPC and expose REST/gRPC APIs to external systems. Resilience4j patterns are applied at service boundaries to ensure fault tolerance and graceful degradation. Each service is packaged as a Docker container and deployed on a Kubernetes cluster. A high-level architecture diagram can be found in the `docs` folder.

## Features

- Payment initiation service with input validation and idempotency.
- Secure payment processing and transaction persistence.
- gRPC based communication between services for low latency.
- Circuit breaker, retries, and rate limiting via Resilience4j.
- Dockerized services with Kubernetes manifests for deployment.
- Comprehensive tests for business logic and integration flows.

## Getting Started

1. **Prerequisites**
   - Java 17 and Maven installed
   - gRPC and Kubernetes CLI tools (optional for running locally)
2. **Clone the repository**

   ```bash
   git clone https://github.com/Chaitanyareddy26/saic-payment-microservices.git
   cd saic-payment-microservices
   ```

3. **Build the project**

   ```bash
   mvn clean package
   ```

4. **Run services**

   Each microservice is in its own module. Navigate to a module and start it using:

   ```bash
   mvn spring-boot:run
   ```

5. **Docker & Kubernetes**

   Dockerfiles and Kubernetes manifests are located under the `deploy/` directory. You can build images and deploy them with:

   ```bash
   cd deploy
   docker build -t saic/payment-service ./payment-service
   kubectl apply -f k8s/
   ```

## My Role & Impact

As a lead developer at SAIC, I designed and implemented the payment microservices architecture, introduced gRPC for efficient communication, and integrated Resilience4j to improve system resilience. By containerizing services and automating deployments on Kubernetes, deployment time was reduced by 50% and transaction throughput improved by 30%.

## Contributing

Please refer to `CONTRIBUTING.md` for guidelines on how to contribute.

## License

This project is licensed under the MIT License. See `LICENSE` for details.
`

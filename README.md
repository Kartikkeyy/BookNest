# Hotel Booking Microservices Application

A distributed hotel room booking system built using Spring Boot for backend microservices and Angular for the frontend.

The system demonstrates secure service-to-service communication, independent data management per microservice, and a complete booking-to-payment workflow.

---

## Overview

This project follows a microservices architecture where each service is independently deployed and manages its own data. Services communicate using REST APIs and are secured using JWT-based authentication.

The application supports:

* User registration and authentication
* Hotel room booking
* Payment processing
* Email notifications
* Customer reviews

---

## Architecture

The system consists of five independent microservices:

| Port | Service              |
| ---- | -------------------- |
| 8080 | Customer Service     |
| 8081 | Booking Service      |
| 8082 | Notification Service |
| 8083 | Payment Service      |
| 8084 | Review Service       |

### Architecture Characteristics

* JWT-based authentication across services
* RESTful inter-service communication using WebClient
* Database-per-service pattern
* Polyglot persistence (MongoDB and H2)
* Email notifications via MailHog

---

## Service Responsibilities

Customer Service
Handles user registration, login, and JWT token generation.

Booking Service
Manages hotel room booking operations.

Payment Service
Processes booking payments and manages transaction data.

Notification Service
Sends email notifications after booking and payment completion.

Review Service
Allows users to create and view reviews.

---

## Database Configuration

Database

The application uses:

MongoDB for data persistence

H2 database for payment processing

Currently, services share a common database instance while running independently on separate ports.

---

## How to Run

### Prerequisites

* Java installed
* Node installed
* MongoDB running
* MailHog running locally

---

### Start Backend Services

Inside each service directory:

```
mvn clean install
mvn spring-boot:run
```

Ensure services are running on ports 8080–8084.

---

### Start Frontend

```
cd frontend
npm install
ng serve
```

Open in browser:

```
http://localhost:4200
```

---

## Application Flow

1. Register a new account
2. Login and receive authentication token
3. Create a booking
4. Complete payment
5. Receive confirmation email
6. Submit a review

---

## Key Highlights

* Distributed microservices architecture
* Secure JWT-based authentication
* Independent data storage per service
* REST-based service communication
* End-to-end booking and transaction lifecycle

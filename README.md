🎟️ Event Ticketing Platform

KIMEP University — Software Engineering Project

A backend ticketing system for concerts and conferences, built with Java 21 and Spring Boot.

The main goal is to ensure that two customers can never successfully purchase the same seat for the same event.

📌 Project Overview

The platform allows:

Organizers to create and publish events.
Customers to browse events and select seats.
Customers to reserve seats for 10 minutes.
Customers to book and pay for reservations.
The system to generate tickets after successful payment.
Administrators to manage venues and users.
🛠️ Technologies
Technology	Purpose
Java 21	Programming language
Spring Boot 3.x	Backend framework
Spring Web	REST API
Spring Data JPA	Database operations
PostgreSQL	Main database
Redis	Seat reservations and caching
RabbitMQ	Asynchronous messaging
Spring Security	Authentication and authorization
JWT	Token authentication
Flyway	Database migrations
Docker	Application deployment
Maven	Build management
JUnit 5	Testing
Testcontainers	Integration testing
🏗️ Architecture

The application follows a feature-based package structure:

text
src/main/java/kimep/
├── TicketingApplication.java
├── catalog/
│   ├── api/
│   ├── domain/
│   ├── repo/
│   └── service/
├── booking/
│   ├── api/
│   ├── domain/
│   ├── repo/
│   └── service/
├── payment/
├── identity/
├── messaging/
├── shared/
└── support/

🔐 Main Features
1. User Authentication
User registration and login.
JWT access and refresh tokens.
Role-based access control.
BCrypt password encryption.
2. Event Management
Create and publish events.
Manage venues and sections.
Browse events with pagination.
View seat availability.
3. Seat Reservations
Reserve seats for 10 minutes.
Redis atomic operations using SET NX.
Automatic expiration using Redis TTL.
Prevent simultaneous reservations of the same seat.
4. Booking and Payments
Convert valid reservations into bookings.
Process payments.
Generate tickets after successful payment.
Prevent duplicate ticket issuance.
5. Asynchronous Messaging
RabbitMQ event processing.
Transactional outbox pattern.
Retry mechanism.
Dead-letter queue.
Idempotent message consumers.
6. Performance and Reliability
Redis caching.
Database indexing.
Prevention of N+1 queries.
Optimistic locking.
Automated tests.
🗄️ Database Entities

The required domain model contains 14 entities:

User
RefreshToken
Venue
Section
Seat
Event
EventSectionPrice
SeatHold
Booking
Ticket
Payment
OutboxMessage
ProcessedMessage
AuditEntry
🚀 Running the Project
Requirements
Java 21
Maven
Docker Desktop
Git
Clone the repository
bash
git clone https://github.com/zhasminmaulen-crypto/kimep-event-ticket

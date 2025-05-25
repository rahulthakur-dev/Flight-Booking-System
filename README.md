# ✈️ Flight Booking Backend

This repository is a monorepo that showcases a flight booking backend system built with a microservices architecture. It includes two independent services — `flight-service` and `booking-service` — both following clean code practices and structured using a custom [Node.js Project Template](https://github.com/rahulthakur-dev/nodejs-project-template).

---

## 📁 Repositories

- [Flight Service](https://github.com/rahulthakur-dev/flight-service)  
  Handles creation and management of flights, airports, and airline data.  
  Includes endpoints for managing routes, seat capacity, and scheduling.

- [Booking Service](https://github.com/rahulthakur-dev/booking-service)  
  Manages user bookings, ensures transactional safety during booking, and prevents overbooking.  
  Implements idempotent operations, locking, and automatic cleanup of stale records.

- [Node.js Project Template](https://github.com/rahulthakur-dev/nodejs-project-template)  
  A reusable, production-ready Node.js boilerplate with a clean folder structure, Sequelize integration, and environment setup.

---

## 🛠️ Tech Stack

- **Backend Framework**: Node.js with Express.js  
- **Database**: MySQL  
- **ORM**: Sequelize  
- **Architecture**: Modular with clear separation of concerns — Controllers, Services, Repositories, Middlewares  
- **Job Scheduling**: Node-Cron for background tasks like stale booking cleanup  
- **Environment Management**: dotenv  
- **Logging & Error Handling**: Custom error classes and centralized logging setup

---

## 📌 Concepts & Features Implemented

### 🔁 Idempotency
- Booking API uses **idempotency keys** to prevent duplicate charges or multiple bookings when the same request is retried.

### 💳 Transaction Management (ACID)
- **Atomicity, Consistency, Isolation, Durability** are ensured using Sequelize transactions during booking operations.
- Database rollbacks and error handling maintain integrity.

### 🔒 Row-Level Locking
- Utilized Sequelize’s `LOCK.UPDATE` to avoid race conditions and overbooking in concurrent booking scenarios.

### 🕐 Cron Jobs
- Automated deletion of **expired or unpaid bookings** using scheduled tasks (node-cron).

### 🧼 Clean Code & Scalable Structure
- Inspired by best practices: single responsibility, clear separation between business logic and infrastructure.
- Each microservice is independently scalable and testable.

### 🌐 RESTful APIs
- Well-defined routes with input validation, middleware, and controller-service flow.

---

## 🧪 Testing & Validation

- Basic input validation using custom middleware
- Sequelize model validation and transaction rollback on failures
- Environment-specific configurations

---

## 🚀 Setup & Deployment

Each microservice contains its own `README.md` for setup and deployment instructions. The services can be run individually.

---

## 📄 License

This project is open source and free to use under the [MIT License](LICENSE).

---

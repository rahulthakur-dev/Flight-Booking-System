## Flight Booking Backend

This repository contains a flight booking backend system designed with a microservices architecture. It consists of two independent services — `flight-service` and `booking-service` — both built using a clean code structure based on a shared [Node.js Project Template](https://github.com/rahulthakur-dev/nodejs-project-template).

## Repositories

- [Flight Service](https://github.com/rahulthakur-dev/flight-service)  
  Responsible for managing flights, airports, and airlines.  
  Includes endpoints for route management, seat capacity, and schedules.

- [Booking Service](https://github.com/rahulthakur-dev/booking-service)  
  Manages flight bookings, transactional safety, and overbooking prevention.  
  Implements idempotency keys, locking, and stale record cleanup.

- [Node.js Project Template](https://github.com/rahulthakur-dev/nodejs-project-template)  
  A reusable boilerplate with a modular structure, Sequelize ORM integration, and environment setup.

## Technology Stack

- Node.js with Express.js  
- MySQL database  
- Sequelize ORM  
- Modular architecture: Controllers, Services, Repositories, Middleware  
- Node-Cron for scheduled background tasks  
- dotenv for environment variable management  
- Custom logging and error handling

## Key Features and Concepts

**Idempotency**  
Prevents duplicate booking or charges by using idempotency keys on critical APIs.

**ACID Transactions**  
Ensures atomicity, consistency, isolation, and durability using Sequelize transactions with rollback on failure.

**Row-Level Locking**  
Uses Sequelize’s row locking to prevent race conditions and overbooking during concurrent requests.

**Cron Jobs**  
Schedules cleanup of expired or unpaid bookings automatically with node-cron.

**Clean and Scalable Code**  
Follows best practices such as single responsibility and clear separation of concerns.  
Allows independent scalability and maintainability of each microservice.

**RESTful API Design**  
Structured routes with input validation, middleware layers, and controller-service separation.

## Testing and Validation

- Input validation through middleware  
- Sequelize model validation with transaction rollback  
- Environment-specific configurations for development, testing, and production

## Setup and Deployment

Each microservice has its own detailed `README.md` for setup and deployment instructions.  
The services are designed to run independently.

## License

This project is open source and available under the [MIT License](LICENSE).

## Tech stack
Java, Spring Boot, Docker, PostgreSQL, Kafka, RabbitMQ, REST, JUnit + Mockito



## About the project

This is a pet microservices project demonstrating interaction between multiple services using modern technologies:

- Multiple microservices with separate PostgreSQL databases  
- Inter-service communication via REST API  
- Asynchronous communication using RabbitMQ (Order → Notification)  
- Event logging with Kafka and a separate `log-consumer` service  
- Test coverage using JUnit and Mockito in the **order-service**
- Running services in Docker containers for easy local development  

## Microservices and communication

| Service         | Description                        | Communication                                                         | Repository                              |
|-----------------|----------------------------------|----------------------------------------------------------------------|---------------------------------------|
| **auth**        | Authentication and authorization | REST API                                                             | [auth-service](https://github.com/denystrypolskyi/auth-service)      |
| **user**        | User management                  | REST API                                                             | [user-service](https://github.com/denystrypolskyi/user-service)      |
| **product**     | Product management               | REST API                                                             | [product-service](https://github.com/denystrypolskyi/product-service)|
| **order**       | Order creation and management    | REST API + RabbitMQ (sending events to notifications) + Kafka (sending logs to topics) | [order-service](https://github.com/denystrypolskyi/order-service)    |
| **notification**| Sending notifications (email)    | RabbitMQ (queue subscriber)                                          | [notification-service](https://github.com/denystrypolskyi/notification-service)|
| **log-consumer**| Reading logs from Kafka          | Kafka                                                               | [log-consumer-service](https://github.com/denystrypolskyi/log-consumer-service)|

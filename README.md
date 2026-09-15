# Quiz Microservices

A Spring Boot based microservices project demonstrating service discovery, API gateway, quiz/question services, and event-driven notifications using Apache Kafka.

## Architecture

```text
                         ┌──────────────────────┐
                         │     API Gateway      │
                         │   quiz-apiGateWay    │
                         └──────────┬───────────┘
                                    │
                    ┌───────────────┴───────────────┐
                    │                               │
           ┌────────▼─────────┐          ┌──────────▼──────────┐
           │   Quiz Service   │          │  Question Service   │
           │ quiz-quizService │          │quiz-questionService │
           └────────┬─────────┘          └─────────────────────┘
                    │
                    │ Quiz Completed Event
                    ▼
               ┌──────────┐
               │  Kafka   │
               └────┬─────┘
                    │
                    ▼
          ┌────────────────────────┐
          │   Notification Service │
          │ quiz-notificationService│
          └───────────┬────────────┘
                      │
                      ▼
                 Firebase FCM


          ┌────────────────────────┐
          │     Eureka Server      │
          │   quiz-serverRegistry   │
          └────────────────────────┘
```

## Services

### API Gateway

[quiz-apiGateWay](https://github.com/aadarsha0997/quiz-apiGateWay)

Entry point for client requests and routing to the appropriate microservice.

### Eureka Server

[quiz-serverRegistry](https://github.com/aadarsha0997/quiz-serverRegistry)

Provides service discovery using Netflix Eureka.

### Quiz Service

[quiz-quizService](https://github.com/aadarsha0997/quiz-quizService)

Handles quiz-related operations.

### Question Service

[quiz-questionService](https://github.com/aadarsha0997/quiz-questionService)

Handles question management and question-related operations.

### Notification Service

[quiz-notificationService](https://github.com/aadarsha0997/quiz-notificationService)

Consumes quiz completion events through Apache Kafka and sends notifications using Firebase Cloud Messaging.

## Technologies

* Java
* Spring Boot
* Spring Cloud
* Spring Cloud Gateway
* Netflix Eureka
* Apache Kafka
* PostgreSQL
* Docker
* Firebase Cloud Messaging
* REST API

## Repositories

| Service              | Repository                                                                           |
| -------------------- | ------------------------------------------------------------------------------------ |
| API Gateway          | [quiz-apiGateWay](https://github.com/aadarsha0997/quiz-apiGateWay)                   |
| Eureka Server        | [quiz-serverRegistry](https://github.com/aadarsha0997/quiz-serverRegistry)           |
| Quiz Service         | [quiz-quizService](https://github.com/aadarsha0997/quiz-quizService)                 |
| Question Service     | [quiz-questionService](https://github.com/aadarsha0997/quiz-questionService)         |
| Notification Service | [quiz-notificationService](https://github.com/aadarsha0997/quiz-notificationService) |

## Purpose

This project was created to practice building and integrating Spring Boot microservices using service discovery, API gateway, inter-service communication, and event-driven architecture with Apache Kafka.


# ✈️ Airline Microservices

## Production-Style Airline / Travel Booking System

A production-oriented airline and travel booking platform built to demonstrate how modern enterprise systems are designed, developed, secured, deployed and scaled.

The project focuses on Java backend engineering, microservices architecture, event-driven communication, distributed caching, containerization, Kubernetes and AWS.

---

## 🎯 Project Goals

This project demonstrates:

- Microservices architecture
- REST API design
- Event-driven architecture
- Synchronous and asynchronous communication
- Distributed caching
- Authentication and authorization
- Database design
- Fault tolerance and resilience
- Containerization
- Kubernetes deployment
- AWS cloud architecture
- Monitoring and observability
- High-Level Design (HLD)
- Low-Level Design (LLD)

---

## 🏗️ Architecture

```text
                    ┌──────────────────┐
                    │   Client / UI    │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │   API Gateway    │
                    └────────┬─────────┘
                             │
          ┌──────────────────┼──────────────────┐
          │                  │                  │
          ▼                  ▼                  ▼
   Authentication      Flight Search       Booking
      Service             Service           Service
          │                  │                  │
          │                  ▼                  │
          │                Redis                │
          │                                     │
          │                  ┌──────────────────┘
          │                  │
          ▼                  ▼
       User DB          Inventory Service
                             │
                             ▼
                           Kafka
                             │
              ┌──────────────┼──────────────┐
              ▼              ▼              ▼
          Payment       Notification      Other
           Service         Service       Consumers

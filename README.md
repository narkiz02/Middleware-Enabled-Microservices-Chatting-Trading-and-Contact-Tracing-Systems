

## Project Title

**Middleware-Enabled Microservices: Chatting, Trading, and Contact Tracing Systems**


## Overview

This project consists of three **independent yet middleware-integrated microservices**: a **Chatting System**, a **Stock Trading Simulation**, and a **Contact Tracing Application**. All systems were built using **Python**, **RabbitMQ** (as the message broker), and **Docker** for containerization.

Each application was designed to demonstrate real-time data exchange and asynchronous communication using **publish-subscribe architecture** across command-line and GUI interfaces.

---

## Technologies Used

*  Python 3
*  RabbitMQ
* Docker
* Tkinter (for GUI)
* Python Threading
* CLI + GUI interaction
* Message Queues & Topics

---

## Chatting Microservice

Simulate a real-time group chat using RabbitMQ fanout exchange.

### Features:

* Each user acts as both **producer and consumer**
* Messages broadcast to all clients using **fanout exchange**
* GUI built with **Tkinter**
* Background consumer thread ensures **responsive GUI**

### Message Flow:

```
User Input (GUI) → Producer → RabbitMQ (fanout) → All Consumers → Chat GUI
```

---

##  Trading Microservic

Simulate a basic **stock exchange system** that handles order submission, trade matching, and price updates.

### Features:

* Producers submit **buy/sell orders**
* Consumer matches trades and **publishes results**
* GUI displays **latest executed price** for "XYZ Corp"
* Two RabbitMQ topics used: `orders` and `trades`

### Logic:

* Match buy/sell orders based on price
* Confirm execution and publish to GUI

---

##  Contact Tracing Microservice

Simulate a **COVID-style contact tracing** app on a 2D grid.

### Features:

* Simulated persons move like a **chess king** on a board
* Each person's location published via RabbitMQ
* A tracker updates positions and logs **contact overlaps**
* GUI displays position grid and supports **user queries** by ID
* Scalable to **1000x1000 grid**

### Components:

* `person.py`: Simulates movement
* `tracker.py`: Logs positions and detects contacts
* `query.py`: Returns contact list based on person ID

---

##  Testing

| Component       | Test Type                        |
| --------------- | -------------------------------- |
| Chat GUI        | Message sending/receiving        |
| Trading Engine  | Order matching and price display |
| Contact Tracing | Position updates + contact query |

---

##  Key Learning Outcomes

* Designed distributed microservices with real-time messaging
* Integrated RabbitMQ into multi-process systems
* Used Docker for consistent environment setup
* Built responsive GUIs using threading and Tkinter
* Learned scalable simulation and message routing




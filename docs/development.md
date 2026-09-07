# Development Guide

This document outlines the development workflow, project architecture, and standards for the **Smart Cart IoT** project.

---

## 1. Architecture Overview

The project is designed with a **Simulation-first** approach:
1. **Simulator**: A Python application emulates physical cart sensors (RFID/Barcode reader, load cell weight sensor) and communicates telemetry/events over MQTT.
2. **Mosquitto Broker**: Relays MQTT messages between the simulator/carts and backend services.
3. **FastAPI Backend**: Subscribes to MQTT topics, processes cart logic, verifies weight consistency, manages sessions, and writes to PostgreSQL.
4. **WebSocket Service**: Pushes live updates from the backend to the Customer Interface and Admin Dashboard.
5. **Frontend Interfaces**:
   - **Customer Interface**: Displays cart contents, running total, weight alerts, and payment QR code.
   - **Admin Dashboard**: Monitors active cart status, battery levels, anomalies, and store-wide analytics.

---

## 2. Prerequisites

- **Git**: For version control.
- **Python 3.10+**: For backend and simulator development.
- **Docker & Docker Compose**: For containerized orchestration.
- **Node.js (LTS)**: For frontend interfaces.

---

## 3. Repository Structure

```
smart-cart-iot/
├── backend/            # FastAPI backend service
├── simulator/          # Python smart cart simulator
├── frontend/           # Web frontend applications
├── mosquitto/          # MQTT broker configurations
├── database/           # PostgreSQL schemas and migrations
├── docs/               # Project documentation
├── docker-compose.yml  # Container setup (foundation)
├── .gitignore          # Git ignore rules
└── README.md           # Project overview
```

---

## 4. Development Standards & Guidelines

- **No Hard-coded Credentials**: Sensitive data (database passwords, API keys, broker tokens) must always be supplied via environment variables (`.env`).
- **Separation of Concerns**: Keep hardware simulation, business logic, and presentation layers modular and decoupled.
- **Clean Commits**: Commit logical units of work with concise and descriptive commit messages.

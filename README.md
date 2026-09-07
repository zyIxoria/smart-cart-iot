# Smart Cart IoT

Smart Cart IoT is a modern, IoT-driven intelligent shopping cart system designed to streamline retail operations, eliminate checkout queues, and enhance the in-store shopping experience.

---

## Core Highlights & Architecture

- **Smart Cart IoT**: An automated retail solution that tracks shopper items in real-time, provides immediate cost calculations, and secures checkout workflows.
- **Simulation-first**: Developed following a simulation-first methodology to test, benchmark, and validate sensor protocols, telemetry events, and network reliability prior to physical hardware fabrication.
- **Python Smart Cart Simulator**: A dedicated Python-based simulator emulating smart cart hardware events, including RFID/barcode item scanning, weight sensor measurements for fraud prevention, and battery/network telemetry.
- **MQTT/Mosquitto**: Employs Eclipse Mosquitto as the messaging broker for ultra-lightweight, decoupled pub/sub communication between carts (or simulator instances) and the central system.
- **FastAPI**: Asynchronous Python backend serving as the central orchestration engine for cart sessions, item verification, pricing calculations, and transaction records.
- **PostgreSQL**: Robust relational database persisting product catalogs, user accounts, active cart states, and historical transactions.
- **WebSocket**: Full-duplex communication channel delivering instantaneous live updates between the FastAPI backend, customer interfaces, and admin dashboards.
- **Customer Interface**: A shopper-facing interactive interface displaying scanned cart items, live subtotal/discounts, anti-theft weight verification status, and seamless digital checkout QR code.
- **Admin Dashboard**: A centralized administrative portal for store managers to observe cart fleet locations, battery levels, connection status, fraud alerts, and operational analytics.

---

## Repository Structure

```
smart-cart-iot/
├── backend/            # FastAPI application, business services, and API endpoints
├── simulator/          # Python Smart Cart hardware and sensor simulator
├── frontend/           # Customer Interface and Admin Dashboard web clients
├── mosquitto/          # MQTT broker configuration and access control
├── database/           # PostgreSQL schemas, migrations, and seed scripts
├── docs/               # Architecture documents, API specs, and development guides
├── docker-compose.yml  # Multi-container orchestration (to be implemented)
├── .gitignore          # Git ignore specifications
└── README.md           # Project overview and documentation
```

---

## Development & Documentation

For setup instructions and development guidelines, refer to [docs/development.md](docs/development.md).

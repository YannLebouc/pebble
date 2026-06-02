# Argos Cold

**Argos Cold** is an edge-based temperature monitoring platform designed for cold rooms, refrigerated storage, restaurants, food service businesses, and small industrial environments.

The project explores how low-cost IoT hardware can provide reliable environmental monitoring, local data collection, historical analysis, and real-time alerting without relying on cloud-first architectures.

---

## Why Argos Cold?

Temperature excursions inside refrigerated environments can lead to:

* food spoilage,
* regulatory compliance issues,
* financial losses,
* equipment failures that remain undetected for hours.

Argos Cold provides a lightweight and affordable monitoring solution built around open technologies and local-first infrastructure.

---

## Architecture Overview

```text
ESP32 + Sensors
        |
        | MQTT
        v
   Mosquitto Broker
        |
        v
    Argos Core
        |
        +--> SQLite
        |
        +--> Alerting
        |
        +--> Grafana
```

### Components

#### ESP32 Sensor Nodes

Field devices responsible for:

* temperature acquisition,
* humidity acquisition,
* local measurements publication.

Protocols:

* MQTT

Hardware:

* ESP32
* DS18B20
* DHT22 (optional)

---

#### Argos Core

Central monitoring service written in Go.

Responsibilities:

* MQTT subscription
* message validation
* metric persistence
* alert evaluation
* device management
* monitoring APIs

---

#### SQLite

Local storage for:

* measurements
* alerts
* device information

Designed for:

* simplicity
* portability
* edge deployments

---

#### Grafana

Visualization layer providing:

* historical temperature charts
* alert history
* device dashboards
* operational monitoring

---

## Current Features

* MQTT telemetry ingestion
* Local SQLite persistence
* Historical measurements storage
* Structured logging
* Edge-first architecture
* Grafana integration

---

## Planned Features

### Monitoring

* [ ] Multi-sensor support
* [ ] Device health monitoring
* [ ] Battery monitoring

### Alerting

* [ ] Telegram notifications
* [ ] Email notifications
* [ ] SMS notifications
* [ ] Escalation policies

### Industrial Protocols

* [ ] Modbus TCP integration
* [ ] Energy meter support
* [ ] Building Management System interoperability

### Operations

* [ ] Docker deployment
* [ ] Automated backups
* [ ] Remote updates

---

## Technical Stack

### Backend

* Go
* MQTT
* SQLite

### Embedded

* ESP32
* C++
* PlatformIO

### Observability

* Grafana
* Structured logging

### Messaging

* Mosquitto MQTT Broker

---

## Goals

Argos Cold serves three purposes:

### Learning Platform

Exploring:

* IoT architectures
* MQTT communication
* edge computing
* industrial protocols
* monitoring systems

### Smart Building Laboratory

Providing a practical foundation for:

* GTB / BMS concepts
* telemetry systems
* environmental monitoring
* connected infrastructure

### Real-World Product Exploration

Evaluating the viability of a low-cost monitoring platform for:

* restaurants
* cold storage facilities
* wine cellars
* hospitality
* small commercial buildings

---

## Philosophy

Argos follows a simple principle:

> Build practical systems that solve real operational problems.

The project favors:

* simplicity,
* maintainability,
* observability,
* reliability,

over unnecessary complexity.

---

## Status

Active development.

Current focus:

* MQTT infrastructure
* ESP32 integration
* temperature monitoring
* alerting workflows
* Grafana dashboards

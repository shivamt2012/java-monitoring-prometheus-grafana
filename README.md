# 2-Tier Java Monitoring System (Spring Boot + Prometheus + Grafana)

A complete observability project built using Spring Boot, Prometheus, and Grafana to monitor JVM and application metrics in real time.

---

# Architecture

Spring Boot Application (Java 21)
        ↓ (/actuator/prometheus)
Prometheus (Metrics Collection & Time-Series Storage)
        ↓
Grafana (Visualization & Dashboards)

---

# Tech Stack

- Java 21
- Spring Boot
- Spring Boot Actuator
- Micrometer Metrics
- Prometheus
- Grafana
- Docker
- WSL2 (Linux environment)

---

# Features

- JVM memory monitoring (heap & non-heap)
- CPU usage tracking
- Application health checks (/actuator/health)
- Metrics exposure (/actuator/prometheus)
- Real-time Prometheus scraping
- Grafana dashboards for visualization
- Time-series monitoring of application performance

---

# How to Run

## 1. Run Spring Boot App

cd app
./mvnw clean install
./mvnw spring-boot:run

App runs at:
http://localhost:8080

---

## 2. Run Prometheus (Docker)

docker run -d \
  --name prometheus \
  -p 9090:9090 \
  -v $(pwd)/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml \
  prom/prometheus

Prometheus:
http://localhost:9090

---

## 3. Run Grafana (Docker)

docker run -d \
  --name grafana \
  -p 3000:3000 \
  grafana/grafana

Grafana:
http://localhost:3000

Login:
Username: admin
Password: admin

---

# Endpoints

- Application: http://localhost:8080
- Health: http://localhost:8080/actuator/health
- Metrics: http://localhost:8080/actuator/prometheus
- Prometheus: http://localhost:9090
- Grafana: http://localhost:3000

---

# What This Project Demonstrates

- Application observability using Spring Boot Actuator
- JVM metrics using Micrometer
- Prometheus-based monitoring system
- Grafana dashboards for visualization
- Docker-based monitoring setup
- Real-world debugging of distributed systems

---

# Screenshots

Add screenshots in /docs folder:
- Grafana dashboard (JVM memory graph)
- Prometheus target UP status
- Health endpoint response

---

# Key Learnings

- How applications expose metrics
- How Prometheus scrapes data
- How Grafana visualizes system performance
- Debugging Docker + WSL networking issues
- Observability fundamentals (metrics, health, uptime)

---

# Author

Shivam Tiwari
DevOps Engineer | Cloud & Monitoring Enthusiast

---

# License

This project is licensed under the MIT License

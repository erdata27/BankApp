# Cloud-Native Microservices System - Accounts, Loans, Cards

This project demonstrates a **production-ready**, **cloud-native** microservices architecture using Java, Spring Boot, and Spring Cloud, implementing 15-factor app principles. It consists of three key microservices: **Accounts**, **Loans**, and **Cards**, each deployed independently with high scalability, resilience, and observability.

---

## 🚀 Technologies Used

- **Languages**: Java
- **Frameworks**: Spring Boot, Spring Cloud (Netflix, Config, Gateway, Eureka, Stream)
- **Security**: OAuth2, Keycloak
- **Messaging**: Apache Kafka, Spring Cloud Stream
- **Containerization**: Docker, Docker Compose
- **Orchestration**: Kubernetes, Helm
- **Observability**: Prometheus, Grafana, Loki, Tempo, Promtail

---

## 📦 Microservices

- **Accounts Service**
- **Loans Service**
- **Cards Service**

Each microservice includes:
- Spring Boot REST APIs
- Docker support
- Kafka-based messaging

---

## 🔐 Security

All services are secured using **OAuth2** with **Keycloak**. API Gateway validates access tokens and enforces role-based access control.

Supported OAuth2 Grant Types:
- Client Credentials
- Authorization Code

---

## 🛠 Features

- ✅ Centralized Configuration using **Spring Cloud Config Server**
- 🔁 Service Discovery with **Eureka Server** and **Kubernetes**
- 🔄 Resilience via **Resilience4j** (Circuit Breaker, Retry, Rate Limiter)
- 🌐 API Routing via **Spring Cloud Gateway**
- 🔐 Token Authentication using **Keycloak**
- 🐳 Dockerized services with **Docker Compose** support
- ☸️ Kubernetes deployments using **Helm**
- 📡 Event-driven messaging with **Apache Kafka**
- 📈 Monitoring with **Prometheus + Grafana**
- 📜 Centralized Logging using **Loki, Promtail**
- 🔍 Tracing with **Tempo**

---

## 🧪 How to Run Locally

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/cloud-native-microservices.git
cd cloud-native-microservices
````

### 2. Start Config Server

```bash
cd config-server
./mvnw spring-boot:run
```

### 3. Start Eureka Server

```bash
cd eureka-server
./mvnw spring-boot:run
```

### 4. Start Microservices

```bash
cd accounts
./mvnw spring-boot:run

cd loans
./mvnw spring-boot:run

cd cards
./mvnw spring-boot:run
```

### 5. Start API Gateway

```bash
cd gateway-server
./mvnw spring-boot:run
```

---

## 🐳 Docker Commands

### Build Images

```bash
docker build -t accounts-service ./accounts
docker build -t loans-service ./loans
docker build -t cards-service ./cards
```

### Run with Docker Compose

```bash
docker-compose up --build
```

---

## ☸️ Kubernetes Setup

### 1. Deploy Helm Charts

```bash
cd helm
helm install accounts ./accounts-chart
helm install loans ./loans-chart
helm install cards ./cards-chart
```

### 2. Monitor with Prometheus + Grafana

```bash
kubectl port-forward svc/grafana 3000:3000
# Access Grafana: http://localhost:3000
# Default creds: admin / admin
```

---

## 📬 Kafka Commands

### Produce Event

```bash
kafka-console-producer.sh --topic transactions --bootstrap-server localhost:9092
```

### Consume Event

```bash
kafka-console-consumer.sh --topic transactions --from-beginning --bootstrap-server localhost:9092
```

---

## 📊 Observability Stack

* **Prometheus**: Metrics collection
* **Grafana**: Dashboards and visualization
* **Loki + Promtail**: Log aggregation
* **Tempo**: Distributed tracing

---


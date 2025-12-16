# Kyrexo & Noha: The AI-Native Development Platform

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Security](https://img.shields.io/badge/security-DevSecOps%20Integrated-red)
![Stack](https://img.shields.io/badge/stack-Angular%20|%20Spring%20Boot%20|%20Python-orange)

> **"Coding at the speed of thought."**

---

## 🚀 Overview

**Kyrexo** is a next-generation Integrated Development Environment (IDE) powered by **Noha**, a proprietary Natural Language Programming interface.

Unlike standard AI coding assistants, **Kyrexo** creates a deterministic bridge between plain English and functional execution across multiple disciplines—Web, IoT, and AI—wrapped in a secure, sandboxed DevSecOps environment.

### 🧠 The Ecosystem

- **Kyrexo (The Body):**  
  A secure web-based IDE featuring real-time collaboration and containerized execution.

- **Noha (The Brain):**  
  An intelligent translation engine that converts intent (English) into syntax (Code), capable of context-switching between disciplines  
  (e.g., converting *“Make the LED blink”* to C++ or *“Center the div”* to CSS).

---

## 🏗 Architecture

The platform follows a **Microservices Architecture** to ensure scalability and separation of concerns.

```mermaid
graph TD
    User["User / Client"] -->|"HTTPS"| Frontend["Kyrexo Frontend (Angular)"]
    Frontend -->|"REST API"| Gateway["API Gateway"]
    Gateway -->|"Auth & Project Mgmt"| Backend["Core Backend (Java Spring Boot)"]
    Gateway -->|"NL Commands"| AI["Noha Engine (Python FastAPI)"]
    
    subgraph ExecutionSandbox ["Execution Sandbox (Secure Docker Environment)"]
        Backend -.->|"Spins up"| Container["User Code Container"]
    end
    
    subgraph DevSecOpsPipeline ["DevSecOps Pipeline"]
        SonarQube["SonarQube (SAST Scanner)"]
        Prometheus["Prometheus (Monitoring)"]
    end
````

---

## 🛠 Tech Stack

### 🎨 Frontend (Kyrexo Interface)

* **Framework:** Angular 17+
* **Editor:** Monaco Editor (the engine behind VS Code)
* **Styling:** TailwindCSS
* **Collaboration:** Y.js (CRDTs for real-time multiplayer editing)

### ⚙ Backend (Core Logic)

* **Language:** Java 21
* **Framework:** Spring Boot 3 (Microservices)
* **Database:** PostgreSQL (User data & project storage)
* **Security:** Spring Security (JWT Authentication)

### 🧠 Noha Engine (AI Layer)

* **Language:** Python 3.11
* **Framework:** FastAPI
* **Model Integration:** OpenAI API / Anthropic Claude (via Adapter Pattern)
* **Logic:** Custom “System Prompt” orchestration for deterministic code generation

### 🔐 DevOps & Security (DevSecOps)

* **Containerization:** Docker & Docker Compose
* **CI/CD:** GitHub Actions
* **Scanning:** SonarQube (Static Analysis), OWASP Dependency Check
* **Monitoring:** Prometheus & Grafana

---

## ✨ Key Features

### 1️⃣ Noha: Context-Aware Translation

Noha doesn’t just *guess* code — it identifies the domain context before generation.

* **Input:** `Read temp data from sensor pin 4`
* **Action:** Context identified → **IoT / Embedded**
* **Output:** Generates valid C++ / Arduino code

---

### 2️⃣ Secure-by-Design Execution

Every time a user runs code, Kyrexo spins up an isolated **Docker container**.

* **Rootless Mode:** Prevents container breakout attacks
* **Resource Quotas:** CPU/RAM limits via Linux cgroups to prevent DoS
* **Auto-Destruct:** Containers are ephemeral and destroyed after execution

---

### 3️⃣ Automated Guardrails

Noha includes an integrated **Security Guard** layer.

It scans generated code for malicious patterns (e.g., `rm -rf`, SQL injection vectors) **before** showing it to the user.

---

## ⚡ Getting Started

### 📦 Prerequisites

* Java 21 JDK
* Node.js & npm
* Python 3.10+
* Docker Desktop

---

### 🛠 Installation

#### 1. Clone the Monorepo

```bash
git clone https://github.com/yourusername/kyrexo-noha-platform.git
cd kyrexo-noha-platform
```

---

#### 2. Start the Infrastructure (Database & SonarQube)

```bash
docker-compose up -d
```

---

#### 3. Run the Microservices

* **Noha Engine**

```bash
cd services/noha-engine
pip install -r requirements.txt
uvicorn main:app --reload
```

* **Kyrexo Backend**

```bash
cd services/kyrexo-core
./mvnw spring-boot:run
```

* **Frontend**

```bash
cd frontend
npm install
ng serve
```

---

#### 4. Access the Platform

Open your browser and navigate to:

```
http://localhost:4200
```

---

## 🗺 Roadmap

* [ ] **Phase 1:** MVP Release (Web development support only)
* [ ] **Phase 2:** IoT context integration (Arduino / C++ support)
* [ ] **Phase 3:** Multiplayer mode (real-time collaborative editing)
* [ ] **Phase 4:** Voice command integration for Noha

---

## 🤝 Contributing

This is a capstone portfolio project.
Suggestions, issues, and pull requests are very welcome.

---

## 📄 License

Distributed under the **MIT License**.

```

If you want, next we can:
- tighten this for **GitHub trending quality**
- split it into `/docs`
- or write a **killer project description** for your CV or MSc applications
```


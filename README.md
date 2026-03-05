# 🚀 Automated Infrastructure Monitoring with Prometheus

A lightweight Infrastructure-as-Code monitoring system that automatically provisions services, monitors them using Prometheus, and validates monitoring behavior through a CI/CD pipeline.

The project simulates a distributed system with detached servers and demonstrates how monitoring can be automated, reproducible, and testable.

# 📌 Project Highlights
⚙️ Infrastructure as Code – automated provisioning of monitoring infrastructure

🐳 Detached containerized servers – simulate distributed services

📡 Prometheus monitoring – pull-based metrics scraping

🔁 CI/CD automation – infrastructure validated through a Drone pipeline

🚨 Failure detection testing – intentionally simulate server failures

🧩 Configurable architecture – system behavior controlled through variables

# ⚙️ Tech Stack
| Technology           | Purpose                             |
| -------------------- | ----------------------------------- |
| Docker               | Containerized detached servers      |
| Prometheus           | Monitoring and metrics collection   |
| Drone CI/CD          | Automated infrastructure validation |
| Python               | Infrastructure automation scripts   |
| Linux (Ubuntu 24.04) | Execution environment               |


# 🔄 How It Works
1️⃣ Provision Infrastructure
The mysolution script:
- creates a Docker network
- deploys detached target servers
- deploys a Prometheus monitoring container

"python3 mysolution"

2️⃣ Validate Monitoring
The mycheck script verifies monitoring correctness.

"python3 mycheck"

It checks:
- target registration in Prometheus
- monitoring detection after a simulated server failure

# 🔧 Configuration
The monitoring environment can be adjusted through variables.

| Variable        | Description                         | Example     |
| --------------- | ----------------------------------- | ----------- |
| TARGET_NAME     | Logical name for monitored services | demo-target |
| TARGET_PORT     | Service port exposed by targets     | 9100        |
| SCRAPE_INTERVAL | Prometheus scraping frequency       | 1s / 5s     |

This allows different monitoring setups without changing the automation logic.

# 🔁 CI/CD Pipeline
The project includes a Drone CI/CD pipeline defined in .drone.yml.

Pipeline workflow:
Push → CI Pipeline → Infrastructure Provisioning → Monitoring Validation

The pipeline:
- runs in Ubuntu 24.04
- installs required dependencies
- executes mysolution
- validates monitoring via mycheck

# 🎯 Key Concepts Demonstrated
- Infrastructure as Code
- Automated monitoring validation
- Detached server architecture
- Container networking
- Observability for distributed systems

# 🎓 Project Context
This project was developed as part of the VLBA Cloud Technologies course, focusing on CI/CD automation, containerized infrastructure, and distributed monitoring systems.

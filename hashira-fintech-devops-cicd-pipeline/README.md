Project: End-to-End DevOps Infrastructure & CI/CD Pipeline

Project Overview

This project demonstrates a complete DevOps infrastructure setup and automated CI/CD pipeline implemented during my Software Engineer Internship (DevOps) at JOGO Consulting LLP for the client Hashira Fintech (Singapore).

The objective of this project was to automate the build, security scanning, containerization, deployment, and monitoring processes for a fintech application while ensuring code quality, security, and observability.

Architecture Diagram

![CI/CD Pipeline](ci-cd-Diagram.jpg)

Infrastructure Setup

A complete DevOps environment was provisioned on AWS to support development, CI/CD automation, and deployment workflows.

AWS Infrastructure Components

Developer VM – Used by developers to write and push code to Bitbucket.

DevOps VM – Hosted Jenkins and SonarQube for CI/CD automation and code quality checks.

Integration/Deployment VM – Used for pulling Docker images and running application containers.

AWS ECR – Secure container registry for storing Docker images.

Monitoring Stack – Prometheus, Loki, Promtail, and Grafana for metrics and log monitoring.

CI/CD Pipeline Workflow

1. Code Push

Developers push application code to the Bitbucket repository.

2. Webhook Trigger

Bitbucket webhook automatically triggers the Jenkins pipeline.

3. Code Checkout

Jenkins checks out the latest code from Bitbucket.

4. Code Quality Analysis

SonarQube performs static code analysis and enforces Quality Gates.

If the quality gate fails:

Pipeline stops

Developer fixes the code and pushes again.

5. Docker Image Build

Jenkins builds a Docker image for the application.

6. Container Security Scan

Trivy scans the Docker image for vulnerabilities.

If vulnerabilities are found:

Pipeline fails

Developer updates dependencies or base images.

7. Push Image to AWS ECR

If the scan passes, the Docker image is pushed to AWS Elastic Container Registry (ECR).

8. Application Deployment

The Integration Server pulls the Docker image from ECR and runs the container on a specific port.

Application access example:

http://<Integration-Server-IP>:<Port>

Monitoring & Observability

The monitoring stack was implemented to track application performance and infrastructure health.

Tools Used

Prometheus – Collects system and application metrics.

Loki – Aggregates logs from containers.

Promtail – Collects logs and sends them to Loki.

Grafana – Visualizes metrics and logs through dashboards.

This setup enables real-time monitoring of:

Application performance

System resource usage

Container logs

Infrastructure health

Tech Stack:

Cloud Platform: AWS (EC2, IAM, ECR)

CI/CD Tool: Jenkins

Source Control: Bitbucket

Code Quality: SonarQube

Containerization: Docker

Security Scanning: Trivy

Monitoring: Prometheus, Loki, Promtail, Grafana

Operating System: Linux

Key Learning Outcomes:

Designed and implemented end-to-end DevOps infrastructure on AWS.

Built an automated CI/CD pipeline integrating multiple DevOps tools.

Implemented container security scanning using Trivy.

Configured observability and monitoring stack using Prometheus and Grafana.

Gained hands-on experience managing cloud infrastructure, containerized deployments, and DevOps workflows.



# Simple Node.js CI/CD Pipeline

This project demonstrates a **CI/CD pipeline** for a simple Node.js application using **Docker** and **GitHub Actions**. The goal is to automate the build and deployment process, enabling smoother development workflows and consistent application delivery.

## 🔗 Project Repository

GitHub Link: [simple-node-ci-cd](https://github.com/suganya-subramanian/simple-node-ci-cd)

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [Installation & Run Locally](#installation--run-locally)
- [Dockerfile](#dockerfile)
- [GitHub Actions CI/CD Workflow](#github-actions-cicd-workflow)
- [Secrets Configuration](#secrets-configuration)
- [Deployment (Optional)](#deployment-optional)

---

## 📘 Project Overview

This project contains a simple Node.js app (`app.js`) that prints a welcome message on a web server. The CI/CD process includes:

1. Automatically building a Docker image when code is pushed to GitHub.
2. Pushing the image to Docker Hub.
3. (Optional) Deployment to a cloud service.

---

## 🛠️ Tech Stack

- Node.js
- Docker
- GitHub Actions

---

## ✅ Prerequisites

- **Docker** installed
- **Node.js & npm** installed (for local development)
- A **Docker Hub** account
- A **GitHub** account

---

## 💻 Installation & Run Locally

### 1. Clone the Repository

```bash
git clone https://github.com/suganya-subramanian/simple-node-ci-cd.git
cd simple-node-ci-cd
```

### 2. Install Node Modules

```bash
npm install
```

### 3. Run the Application Locally

```bash
node app.js
```

Now open your browser and navigate to `http://localhost:3000`

### 4. Run Using Docker

```bash
docker build -t simple-node-ci-cd .
docker run -p 3000:3000 simple-node-ci-cd
```
!(./screenshots/picture3.png)
---

## 📦 Dockerfile

```Dockerfile
# Use official Node.js image
FROM node:14

# Set working directory
WORKDIR /app

# Copy and install dependencies
COPY package.json .
RUN npm install

# Copy all source files
COPY . .

# Expose port and run app
EXPOSE 3000
CMD ["node", "app.js"]
```

---

## 🔄 GitHub Actions CI/CD Workflow

The GitHub Actions workflow is located in `.github/workflows/docker.yml`.

```yaml
name: Docker Build and Deploy

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Log in to Docker Hub
        uses: docker/login-action@v2
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}

      - name: Build Docker image
        run: docker build -t your-dockerhub-username/simple-node-ci-cd .

      - name: Push Docker image
        run: docker push your-dockerhub-username/simple-node-ci-cd

      - name: Deploy Application (Optional)
        run: echo "Deployment step here"
```
(./screenshots/Screenshot From 2025-04-22 16-23-56.png)
---

## 🔐 Secrets Configuration

Go to your GitHub repository:

- Click **Settings** → **Secrets and variables** → **Actions** → **New repository secret**
- Add the following:
  - `DOCKER_USERNAME`
  - `DOCKER_PASSWORD`


(./screenshots/Screenshot From 2025-04-22 15-05-59.png)


---




## 🚀 Deployment (Optional)

Once the Docker image is pushed to Docker Hub, you can deploy it:

- To a cloud provider like **AWS EC2**, **DigitalOcean**, **GCP**, etc.
- Or to **Kubernetes** using Helm or Argo CD

This project includes a placeholder for adding your deployment step in the CI/CD workflow.

---

---

## 👩‍💻 Author

**Suganya Subramanian**

- GitHub: [suganya-subramanian](https://github.com/suganya-subramanian)

---




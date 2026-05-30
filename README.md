# 🚀 CI/CD Pipeline with GitHub Actions, Docker & AWS EC2

## 📌 Project Overview

This project demonstrates a complete CI/CD (Continuous Integration and Continuous Deployment) pipeline using:

- GitHub Actions
- Node.js
- Jest Testing
- Docker
- Docker Hub
- AWS EC2
- SSH Deployment

Whenever code is pushed to the `main` branch:

1. Tests are executed automatically.
2. Docker image is built.
3. Image is pushed to Docker Hub.
4. GitHub Actions connects to AWS EC2 via SSH.
5. Latest Docker image is pulled.
6. Existing container is replaced with the new version.

---

## 🏗️ Architecture

```text
Developer
    │
    ▼
GitHub Repository
    │
    ▼
GitHub Actions
    │
    ├── Run Tests
    ├── Build Docker Image
    └── Push Image to Docker Hub
                │
                ▼
          Docker Hub
                │
                ▼
           AWS EC2
                │
                ▼
        Docker Container
                │
                ▼
          Node.js App
```

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|----------|
| Node.js | Application Runtime |
| Jest | Unit Testing |
| Docker | Containerization |
| GitHub Actions | CI/CD Automation |
| Docker Hub | Image Registry |
| AWS EC2 | Deployment Server |
| SSH | Secure Deployment |

---

## 📂 Project Structure

```text
cicd-nodejs/
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
├── server.js
├── app.test.js
├── package.json
├── Dockerfile
└── README.md
```

---

## ⚙️ CI/CD Workflow

### Step 1: Code Push

```bash
git add .
git commit -m "new feature"
git push origin main
```

### Step 2: GitHub Actions

Automatically executes:

```bash
npm install
npm test
docker build
docker push
```

### Step 3: Deployment

GitHub Actions:

```bash
ssh into EC2
docker pull latest image
docker stop old container
docker run new container
```

---

## 🐳 Docker Commands Used

Build Image:

```bash
docker build -t alekh2412/cicd-nodejs:latest .
```

Run Container:

```bash
docker run -d -p 3000:3000 alekh2412/cicd-nodejs:latest
```

Push Image:

```bash
docker push alekh2412/cicd-nodejs:latest
```

---

## ☁️ AWS Deployment

Application deployed on:

```text
AWS EC2 Ubuntu Instance
```

Access:

```text
http://<EC2-PUBLIC-IP>:3000
```

---

## 🔐 GitHub Secrets Used

```text
DOCKER_USERNAME
DOCKER_PASSWORD
EC2_HOST
EC2_USERNAME
EC2_SSH_KEY
```

---

## ✅ Features

- Automated Testing
- Automated Docker Build
- Automated Docker Push
- Automated EC2 Deployment
- GitHub Actions Workflow
- Zero Manual Deployment
- Infrastructure Ready for Scaling

---

## 📸 Project Screenshots

### GitHub Actions Success

<img width="1912" height="938" alt="image" src="https://github.com/user-attachments/assets/58fc4219-1012-489b-832f-b4ce8df3e5a6" />


### Application Running on EC2

<img width="1918" height="1026" alt="image" src="https://github.com/user-attachments/assets/5f30d18d-4bdd-47a0-8838-2197b99947c3" />


---

## 🎯 Key Learnings

- CI/CD Pipeline Design
- GitHub Actions Workflow Creation
- Docker Containerization
- Docker Hub Integration
- AWS EC2 Deployment
- SSH Automation
- DevOps Best Practices

---

## 👨‍💻 Author

Alekh

DevOps | Cloud | AWS | Docker | GitHub Actions

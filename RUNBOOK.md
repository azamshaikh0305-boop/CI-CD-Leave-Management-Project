# Runbook – CI/CD Leave Management System

## 1. Project Overview

This runbook provides step-by-step instructions to set up, run, and troubleshoot the Leave Management System.
The application is built using Flask and deployed using Docker with CI/CD integration.

---

## 2. Prerequisites

Make sure the following are installed:

- Python (3.10 recommended)
- pip (Python package manager)
- Docker
- Git

---

## 3. Setup Instructions

### Step 1: Clone Repository

```bash
git clone <your-repo-link>
cd CI-CD-Leave-Management-Project
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 3: Run Application (Local)

```bash
python app.py
```

Open in browser:
```
http://localhost:5000
```

---

## 4. Running with Docker

### Step 1: Build Docker Image

```bash
docker build -t leave-app .
```

### Step 2: Run Container

```bash
docker run -d -p 5000:5000 leave-app
```

Access app:
```
http://localhost:5000
```

---

## 5. Running Tests

```bash
pytest tests/
```

---

## 6. Health Check (Monitoring)

Check application status:

```bash
curl http://localhost:5000/health
```

Expected Output:

```json
{"status": "healthy"}
```

---

## 7. CI/CD Pipeline

The CI/CD pipeline runs automatically on every push to GitHub.

Steps involved:

1. Install dependencies
2. Run tests
3. Build Docker image
4. Run container
5. Perform health check

---

## 8. Troubleshooting

**Issue: Module not found**

Solution:
```bash
pip install -r requirements.txt
```

**Issue: Port already in use**

Solution:
```bash
docker run -p 5001:5000 leave-app
```

**Issue: Tests failing**

Solution:
- Check test files in `/tests`
- Verify application structure

**Issue: Docker not running**

Solution:
- Start Docker Desktop
- Retry commands

---

## 9. Logs & Debugging

Check running containers:

```bash
docker ps
```

View logs:

```bash
docker logs <container_id>
```

---

## 10. Future Improvements

- Add Prometheus for monitoring
- Use Terraform for infrastructure
- Deploy to cloud platforms (AWS/Azure)

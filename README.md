# 🚀 Flask API with CI/CD Pipeline

[![CI/CD Pipeline](https://github.com/vikas-wanchoo-devops/FlaskAPI-Docker-CICD/actions/workflows/docker.yml/badge.svg?branch=develop)](https://github.com/vikas-wanchoo-devops/FlaskAPI-Docker-CICD/actions/workflows/docker.yml?branch=develop&cacheSeconds=60&timestamp=20260304)
![Docker Pulls](https://img.shields.io/docker/pulls/vikaswanchoo/flask-api?cacheSeconds=60&timestamp=20260304)
![GitHub Repo stars](https://img.shields.io/github/stars/vikas-wanchoo-devops/FlaskAPI-Docker-CICD?style=social&cacheSeconds=60&timestamp=20260304)
![GitHub License](https://img.shields.io/github/license/vikas-wanchoo-devops/FlaskAPI-Docker-CICD?cacheSeconds=60&timestamp=20260304)
[![Code Freeze Check](https://github.com/vikas-wanchoo-devops/FlaskAPI-Docker-CICD/actions/workflows/code-freeze.yml/badge.svg)](https://github.com/vikas-wanchoo-devops/FlaskAPI-Docker-CICD/actions/workflows/code-freeze.yml)

---

## 📖 What this repo does
- 🐍 Simple **Flask API** application
- 🐳 Builds and pushes **Docker image** to Docker Hub
- ⚙️ Automated **CI/CD pipeline** using GitHub Actions
- ✅ Pipeline runs on **every push to `develop` branch**

---

## 🔄 CI/CD Pipeline Steps
1. 📥 **Checkout** repository  
2. 🐍 **Install dependencies**  
3. 🧪 **Run tests** (optional)  
4. 🔑 **Login to Docker Hub**  
5. 🛠️ **Build Docker image**  
6. 📤 **Push image** to Docker Hub  
7. ▶️ **Run container** for verification  
8. 🧹 **Cleanup** resources  

---

## 📦 Docker Usage

```bash
# Build locally
docker build -t flask-api .

# Run locally
docker run -p 5000:5000 flask-api

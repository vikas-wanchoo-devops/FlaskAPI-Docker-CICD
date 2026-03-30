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
- 🛑 Enforces **code freeze policy** via central governance repo  

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

## 🛑 Code Freeze Enforcement

This repo listens to the **central freeze flag** from [`release-freeze-control`](https://github.com/vikas-wanchoo-devops/release-freeze-control).  

### Workflow: `.github/workflows/code-freeze.yml`
- Triggered by:
  - `repository_dispatch` event (`freeze-updated`) from central repo
  - PR events (`opened`, `synchronize`, `reopened`, `ready_for_review`)
- Steps:
  1. Fetch `freeze.json` from central repo  
  2. Validate JSON format  
  3. Parse `freeze_active` flag and `reason`  
  4. If `freeze_active: true` → ❌ Block merges, show reason  
  5. If `freeze_active: false` → ✅ Allow merges, show reason  

### Example messages
- ❌ *Code freeze is active. Merging is blocked. Reason: Quarterly release window*  
- ✅ *Code freeze is inactive. Merges are allowed. Reason: Release window until March 31*  

This ensures **all PRs** in this repo respect the central freeze policy automatically.

---

## 📦 Docker Usage

```bash
# Build locally
docker build -t flask-api .

# Run locally
docker run -p 5000:5000 flask-api

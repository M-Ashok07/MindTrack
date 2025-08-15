# Brain Task - Deployment Repository

This repository contains all files needed to build, containerize, push to ECR, and deploy a Vite/React app to an EKS cluster. It also includes a `buildspec.yml` for AWS CodeBuild and Kubernetes manifests for EKS.

## What's included
- Dockerfile (multi-stage build) that serves the built Vite app with nginx on port 3000
- nginx.conf (serves SPA, listens on port 3000)
- buildspec.yml (for CodeBuild: builds Docker image, pushes to ECR, outputs k8s manifests)
- k8s manifests (deployment template and service)
- scripts/deploy_k8s.sh (helper to apply manifests using kubectl)
- Minimal Vite React app (`src/` and `public/index.html`)

## Quick local steps
1. Install dependencies and build:
   ```bash
   npm install
   npm run build

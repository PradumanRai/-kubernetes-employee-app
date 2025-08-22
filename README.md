# Kubernetes Employee Management Application

## 📋 Project Overview
Deployment of a NodeJS employee management application with MongoDB database on Kubernetes cluster.

## 🏗️ Architecture
![Architecture Diagram](./docs/architecture.png)

## 🚀 Technologies Used
- Kubernetes
- Docker
- Minikube
- NodeJS
- MongoDB
- CentOS Linux

## 📁 Project Structure

## 🛠️ Installation & Deployment

### Prerequisites
- Minikube
- kubectl
- Docker

### Deployment Steps
1. Start Minikube: `minikube start --driver=docker --force`
2. Deploy MongoDB: `kubectl apply -f manifests/mongo-deployment.yaml`
3. Deploy NodeJS App: `kubectl apply -f manifests/nodejs-deployment.yaml`
4. Access Application: `minikube service nodejs-service --url`

## 📸 Screenshots
- [Application Homepage](./screenshots/homepage.png)
- [Add Employee](./screenshots/add-employee.png)
- [View Employees](./screenshots/view-employees.png)

## 📊 Verification
```bash
kubectl get all
kubectl get pods
kubectl get services

### Create manifests directory with your YAML files
```bash
# Copy your existing YAML files to manifests folder
cp mongo-deployment.yaml manifests/
cp nodejs-deployment.yaml manifests/

# Create a helpful script file
cat > manifests/deploy.sh << 'EOF'
#!/bin/bash
echo "🚀 Deploying Employee Management Application..."
kubectl apply -f mongo-deployment.yaml
kubectl apply -f nodejs-deployment.yaml
echo "✅ Deployment complete! Check status with: kubectl get all"

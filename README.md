# 🚀 Minikube Kubernetes Demo

## 📌 Overview
This project demonstrates how to **create a local Kubernetes cluster with Minikube**, deploy a simple Nginx app, expose it via a service, and manage it with scaling and logs.  
It includes YAML manifests and step-by-step commands to run and verify your app.

---

## 🛠 Prerequisites

- **Minikube** – Local Kubernetes cluster tool
- **kubectl** – Kubernetes CLI
- **Docker** – Required if using the Docker driver for Minikube

---

## 📂 Project Structure

```
minikube-k8s-demo/
├── namespace.yaml
├── deployment.yaml
├── service.yaml
├── configmap.yaml
├── ingress.yaml
└── README.md 
```

---

## 📜 Steps

### 1️⃣ Start Minikube

```bash
minikube start
```

### 2️⃣ Create Namespace

```bash
kubectl apply -f namespace.yaml
```

### 3️⃣ Deploy Nginx App

```bash
kubectl apply -f deployment.yaml
```

### 4️⃣ Expose Deployment

```bash
kubectl apply -f service.yaml
```

### 5️⃣ Create ConfigMap

```bash
kubectl apply -f configmap.yaml
```

### 6️⃣ Setup Ingress

```bash
kubectl apply -f ingress.yaml
```

### 7️⃣ Verify Deployment

```bash
kubectl get pods -n demo-app
kubectl get svc -n demo-app
```

### 8️⃣ Access Application

```bash
minikube service nginx-service -n demo-app
```

### 9️⃣ Scale Deployment

```bash
kubectl scale deployment nginx-deployment --replicas=4 -n demo-app
```

### 🔟 View Logs

```bash
kubectl logs <pod-name> -n demo-app
# Example:
kubectl logs nginx-deployment-96b9d695-95wjb -n demo-app
```

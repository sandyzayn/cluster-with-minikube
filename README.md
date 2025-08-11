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

## 🖼️ Demo Screenshots

> Below are screenshots showing the Minikube cluster, kubectl commands, and Nginx deployment in action:

<img width="1919" height="1020" alt="Minikube Start" src="https://github.com/user-attachments/assets/a6b6615c-9e9e-4fb9-8a86-1c0fea302d86" />

<img width="1915" height="1017" alt="Kubectl Get Pods" src="https://github.com/user-attachments/assets/6a9be8f8-6d15-4022-a68b-546190bb89bf" />

<img width="1919" height="1016" alt="Kubectl Get Services" src="https://github.com/user-attachments/assets/04a2bd29-4451-4423-b5e7-4cb8fc4e6eb1" />

<img width="1581" height="541" alt="Kubectl Logs" src="https://github.com/user-attachments/assets/ca60d704-f763-4f0f-a236-9f0cd9c4447c" />

<img width="1919" height="1019" alt="Nginx Service Access" src="https://github.com/user-attachments/assets/b9f0ff2b-b2ab-4a8c-9d5f-2e36264a9d6d" />

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

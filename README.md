#**🚀 Minikube Kubernetes Demo**
##**📌 Overview**
This project shows how to **create a local Kubernetes cluster with Minikube, deploy a simple Nginx app, expose it via a service, and manage it with scaling and logs.**
It includes YAML manifests and commands to run and verify your app.

###**🛠 Prerequisites**
Minikube – Local Kubernetes cluster tool.

kubectl – Kubernetes CLI.

Docker – Required if using the Docker driver for Minikube.

####**📂 Project Structure**
minikube-k8s-demo/
├── namespace.yaml      
├── deployment.yaml     
├── service.yaml        
├── configmap.yaml      
├── ingress.yaml       
└── README.md 

#####**📜 Steps**
**1️⃣ Start Minikube**
```
minikube start
```
**2️⃣ Create Namespace**
```
kubectl apply -f namespace.yaml
```
**3️⃣ Deploy Nginx App**
```
kubectl apply -f deployment.yaml
```
**4️⃣ Expose Deployment**
```
kubectl apply -f service.yaml
```
**5️⃣ Create ConfigMap**
```
kubectl apply -f configmap.yaml
```
**6️⃣ Setup Ingress**
```
kubectl apply -f ingress.yaml
```
**7️⃣ Verify Deployment**
```
kubectl get pods -n demo-app
kubectl get svc -n demo-app
```
**8️⃣ Access Application**
```
minikube service nginx-service -n demo-app
```
**9️⃣ Scale Deployment**
```
kubectl scale deployment nginx-deployment --replicas=4 -n demo-app
```
**🔟 View Logs**
```
kubectl logs nginx-deployment-96b9d695-95wjb -n demo-app

```


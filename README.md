
# 🚀 DevOps Project README (Go Web App on AWS EKS)

## 📌 Project Overview

Is project me humne ek complete DevOps pipeline banayi hai jisme:
- Go language ka web application
- Docker containerization
- Kubernetes (AWS EKS) deployment
- AWS Load Balancer ke through internet exposure

Final output: Ek live website jo AWS cloud par run ho rahi hai.

---

## 🏗️ Architecture Diagram

User Browser
    ↓
AWS Load Balancer (ELB)
    ↓
Kubernetes Service (LoadBalancer)
    ↓
Kubernetes Deployment
    ↓
Pods (Go Web Application)

---

## ☁️ Final Architecture (Visual)

+----------------------+
|   User Browser       |
+----------+-----------+
           |
           v
+----------------------+
| AWS Load Balancer    |
+----------+-----------+
           |
           v
+----------------------+
| K8s Service          |
+----------+-----------+
           |
           v
+----------------------+
| Kubernetes Pods      |
| (Go App Container)   |
+----------------------+

---

## 🧠 Step-by-Step Process

### 1. Go Web App banaya
- Simple HTTP server
- Routes: / and /health

Problem:
- Pehle "/" route missing tha → 404 error aaya

Fix:
- Root route add kiya

---

### 2. Docker Image banayi
Command:
docker build -t go-web-app .

Kya hua:
- App container me pack ho gaya

---

### 3. AWS EKS Cluster create kiya
Command:
eksctl create cluster --name go-web-cluster --region ap-south-1

Kya hua:
- Kubernetes cluster ready hua AWS par
- EC2 worker nodes auto create hue

---

### 4. Kubernetes Deployment
Command:
kubectl apply -f deployment.yaml

Kya hua:
- Pods create hue
- App run hone lagi cluster me

---

### 5. Kubernetes Service (LoadBalancer)
Command:
kubectl apply -f service.yaml

Kya hua:
- AWS ELB create hua
- Public URL mil gaya

---

### 6. Browser Access
URL:
http://<elb-dns>

Problem:
- Pehle 404 error aaya (route issue)

Fix:
- Go app me "/" route add kiya

---

## ❗ Problems & Solutions

### ❌ Problem 1: 404 error
Reason:
Root route missing tha

Fix:
Go code me "/" handler add kiya

---

### ❌ Problem 2: LoadBalancer issue
Reason:
AWS provisioning delay

Fix:
Wait + service verify

---

### ❌ Problem 3: Grafana pending
Reason:
Node resources kam the

Fix:
Grafana skip kiya

---

## ⚙️ Final Working System

✔ Go app running in Docker container  
✔ Kubernetes deployment active  
✔ AWS LoadBalancer working  
✔ Website internet par live  

---

## 🧠 What I Learned

- Docker containerization
- Kubernetes pods, deployments, services
- AWS EKS cluster setup
- Load balancing concept
- Cloud networking basics

---

## 🚀 Final Result

Ek fully working cloud-native DevOps project jo:
- Scalable hai
- Production-style architecture follow karta hai
- Internet par publicly accessible hai

---

## 👨‍💻 Author
Aman - DevOps Learner

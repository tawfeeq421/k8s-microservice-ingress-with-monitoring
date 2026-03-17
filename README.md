# 🚀 Kubernetes Microservices Project

## 📌 Project Overview

This project demonstrates a **production-style microservices architecture** deployed on Kubernetes.

It includes multiple services exposed through **Ingress with TLS**, supporting both **path-based and host-based routing**.

---

## 🧩 Architecture

* **Amazon Service**
* **Netflix Service**
* **Game Service**
* **NGINX Ingress Controller**
* **TLS (HTTPS) Enabled**
* **Horizontal Pod Autoscaler (HPA)**

---

## 🛠️ Technologies Used

* Kubernetes (K8s)
* Docker
* NGINX Ingress Controller
* YAML
* OpenSSL (TLS)

---

## 📁 Project Structure

```
k8s-microservice-ingress/
│
├── amazon-deployment.yml
├── netflix-deployment.yml
├── game-deployment.yml
├── amazon-service.yml
├── netflix-service.yml
├── game-service.yml
├── ingress.yml
├── tls-secret.yml
└── namespace.yml
```

---

## 🌐 Routing Strategies

### 🔹 1. Path-Based Routing

| URL        | Service         |
| ---------- | --------------- |
| `/`        | amazon-service  |
| `/netflix` | netflix-service |
| `/game`    | game-service    |

---

### 🔹 2. Host-Based Routing

| Host                  | Service         |
| --------------------- | --------------- |
| `amazon.example.com`  | amazon-service  |
| `netflix.example.com` | netflix-service |
| `game.example.com`    | game-service    |

---

## ⚙️ Setup Instructions

### 1️⃣ Create Namespace

```bash
kubectl apply -f namespace.yml
```

---

### 2️⃣ Deploy Applications

```bash
kubectl apply -f .
```

---

### 3️⃣ Install Ingress Controller

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml
```

---

### 4️⃣ Create TLS Secret

```bash
kubectl create secret tls amazon-tls \
  --cert=cert.crt \
  --key=key.key \
  -n prod
```

---

### 5️⃣ Configure Hosts File (For Local Testing)

```bash
sudo vi /etc/hosts
```

Add:

```
<INGRESS-IP> example.amazon.in
<INGRESS-IP> amazon.example.com
<INGRESS-IP> netflix.example.com
<INGRESS-IP> game.example.com
```

---

## 🌍 Access Application

### Path-Based

* https://example.amazon.in/
* https://example.amazon.in/netflix
* https://example.amazon.in/game

### Host-Based

* https://amazon.example.com
* https://netflix.example.com
* https://game.example.com

---

## 🔐 Features

* ✅ Path-Based Routing
* ✅ Host-Based Routing
* ✅ TLS (HTTPS)
* ✅ Rolling Updates
* ✅ Health Checks (Probes)
* ✅ Resource Management
* ✅ Scalable Architecture

---

## 🧠 Key Learnings

* Ingress Routing (Host + Path)
* TLS Setup in Kubernetes
* Microservices Deployment
* Kubernetes Best Practices

---

## 🚀 Future Improvements

* CI/CD (Jenkins / GitHub Actions)
* Helm Charts
* Monitoring (Prometheus + Grafana)
* Logging (ELK Stack)

---

## 👨‍💻 Author

**Tawfeeq Ahmed**

---

## ⭐ Support

If you like this project, give it a ⭐ on GitHub!


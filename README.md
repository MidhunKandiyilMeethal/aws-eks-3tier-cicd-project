# 3-Tier PHP Application on AWS EKS - End-to-End CI/CD

## 🚀 Project Overview
Deployed a scalable 3-Tier PHP application on AWS EKS using production-grade DevOps practices. Part of Entri Elevate AWS with DevOps course (2026).

## 🏗️ Architecture
**Pipeline:** GitHub → Jenkins → Docker Build → Amazon ECR → Helm Chart → AWS EKS → Monitoring

**Tier 1 - Frontend:** PHP Application (Dockerized)
**Tier 2 - Backend:** MySQL with StatefulSet, PVC, Secrets
**Tier 3 - Monitoring:** Prometheus + Grafana Dashboards

## 🛠️ Tech Stack
- **Cloud:** AWS EKS, ECR, VPC, IAM, EBS
- **DevOps:** Jenkins, Docker, Helm, Kubernetes
- **Monitoring:** Prometheus, Grafana
- **DB:** MySQL (StatefulSet)
- **K8s Concepts:** Deployment, Service, Ingress, ConfigMaps, Secrets, PVC

## ⚙️ Key Implementations
- ✅ Dockerized PHP app with multi-stage build
- ✅ Jenkins pipeline triggered on git commit
- ✅ MySQL as StatefulSet with persistent storage
- ✅ Helm chart for one-click deployment
- ✅ ConfigMaps & Secrets for config management
- ✅ Prometheus metrics + Grafana dashboards

## 📸 Architecture Diagram
`Jenkins Server -> ECR -> EKS Cluster (PHP Pod + MySQL Pod) -> Grafana`

## 🔧 How to Deploy
```bash
helm install php-3tier ./helm-chart
kubectl get pods -n php-app

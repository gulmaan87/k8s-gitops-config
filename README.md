# 🚀 Enterprise-Grade Kubernetes Platform on AWS (GitOps)

## Overview
This project demonstrates a **production-ready Kubernetes platform** built on **AWS EKS**, following real-world **platform engineering** practices such as GitOps, progressive delivery, observability, and reliability-first design.

The goal of this project is not to deploy a single application, but to **design and operate a Kubernetes platform** the way modern engineering teams do in production.

---

## 🧩 Architecture Overview

Developer
|
| git commit
v
GitHub (GitOps Repository)
|
v
Argo CD
|
| sync
v
Kubernetes (AWS EKS)
├─ Helm Charts
├─ Argo Rollouts (Blue-Green)
├─ Prometheus
├─ Grafana
├─ Autoscaling & Self-Healing
└─ Secure, Declarative Workloads


### Design Principles
- Git as the **single source of truth**
- Declarative infrastructure & deployments
- Safe releases with instant rollback
- Metrics-driven visibility and confidence
- Cost-aware, reproducible clusters

---

## ✨ Key Features

- **GitOps-based deployments** using Argo CD  
- **Helm-based application packaging**
- **Blue-Green deployments** using Argo Rollouts
- **Manual promotion & instant rollback**
- **Full observability** with Prometheus & Grafana
- **Autoscaling and self-healing workloads**
- **Production-grade monitoring & metrics**

---

## 🔄 GitOps Deployment Flow

1. Developer pushes code or configuration to GitHub  
2. Argo CD detects changes and syncs desired state  
3. Helm renders Kubernetes manifests  
4. Argo Rollouts manages Blue-Green deployment  
5. Traffic switches only after manual approval  

This removes manual `kubectl` and enforces **consistent, auditable deployments**.

---

## 🔵 Progressive Delivery (Blue-Green)

The application uses **Blue-Green deployment strategy**:

- **Active service** handles production traffic
- **Preview service** runs the new version
- Traffic is promoted manually
- Rollback is instant and safe

### Argo CD Rollout View
![Argo Rollouts](docs/images/argo-rollouts.png)

---

## 📊 Observability & Monitoring

The platform is fully observable using **Prometheus and Grafana**, providing deep visibility into:

- Node-level CPU, memory, disk, and network usage
- Kubernetes cluster health
- Deployment and pod status
- Resource utilization and capacity

### Node Metrics (Node Exporter)
![Node Exporter Dashboard](docs/images/node-exporter.png)

### Kubernetes Cluster Health
![Kubernetes Cluster Dashboard](docs/images/k8s-cluster.png)

### Cluster Network & Resource Usage
![Cluster Monitoring](docs/images/cluster-monitoring.png)

---

## 🔍 Prometheus Target Health

All platform components are actively scraped and healthy, ensuring reliable metrics collection.

![Prometheus Targets](docs/images/prometheus-targets.png)

This confirms:
- Prometheus is correctly configured
- All services expose metrics
- Dashboards reflect real cluster state

---

## ⚙️ Autoscaling & Self-Healing

- Pods automatically restart on failure
- Resource requests and limits enforce stability
- Cluster capacity and usage are continuously monitored
- Kubernetes ensures high availability by design

---

## 🔐 Security & Best Practices

- No secrets committed to Git
- Declarative configuration only
- Namespace isolation
- Resource quotas and health probes
- Infrastructure treated as **ephemeral and reproducible**

---

## 🛠️ Tech Stack

- **Cloud:** AWS (EKS, EC2, IAM)
- **Container Orchestration:** Kubernetes
- **GitOps:** Argo CD
- **Progressive Delivery:** Argo Rollouts
- **Packaging:** Helm
- **Observability:** Prometheus, Grafana
- **Version Control:** GitHub

---

## ▶️ How to Run (High-Level)

1. Provision EKS cluster (eksctl / IaC)
2. Install Argo CD
3. Apply GitOps manifests
4. Push changes to GitHub
5. Argo CD automatically syncs the cluster

> The cluster is intentionally **reproducible and disposable** to control cost.

---

## ♻️ Rollback Strategy

- Manual promotion controls production traffic
- Instant rollback using Argo Rollouts
- No redeployment required

---

## 🎯 Why This Project Matters

This project focuses on **platform engineering**, not just application deployment.

It demonstrates:
- How real Kubernetes platforms are built
- How teams deploy safely at scale
- How observability supports release confidence
- How GitOps replaces manual operations

---

## 📌 Resume Summary

> Designed and implemented an enterprise-grade Kubernetes platform on AWS EKS using GitOps, Blue-Green deployments, and full observability with Prometheus and Grafana.

---

## 📎 Screenshots Included

- Argo CD application graph with Blue-Green rollout
- Node-level metrics (Node Exporter)
- Kubernetes cluster health dashboards
- Prometheus target health

---

## ✅ Status
This project represents a **production-style Kubernetes platform** aligned with modern DevOps and Platform Engineering practices.

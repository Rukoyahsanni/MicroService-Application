# Microservices Deployment with Helm and Helmfile on LKE

This project showcases the deployment of a production-style, 10-tier microservices application on [Linode Kubernetes Engine (LKE)](https://www.linode.com/products/kubernetes/). The primary goal was to gain hands-on experience with **Helm**, **Helmfile**, and Kubernetes operations in a cloud-native environment.

---

## 📌 Objective

- Learn and practice Helm chart authoring and customization
- Use Helmfile to manage multiple interdependent Helm charts
- Deploy a full-stack microservices application on LKE
- Understand probe configuration, environment variables, service networking, and release management

---

## 🧱 Tech Stack

| Tool/Service   | Purpose                                 |
|----------------|-----------------------------------------|
| **Kubernetes (LKE)** | Container orchestration |
| **Helm**       | Package manager for Kubernetes |
| **Helmfile**   | Helm release orchestration |
| **Redis**      | Cart storage backend |
| **gcr.io/google-samples/microservices-demo** | Base app |

---

## 📂 Project Structure

MicroService-Application/
├── charts/
│ ├── frontend/
│ ├── cartservice/
│ ├── rediscart/
│ └── ... (other microservices)
├── values/
│ ├── frontend-values.yaml
│ ├── cartservice-values.yaml
│ └── ...
├── helmfile.yaml
└── README.md

---

## 🚀 Getting Started

### 1. Prerequisites

- kubectl
- helm
- helmfile
- Access to an LKE cluster (configured via kubeconfig)

### 2. Install Releases

```bash
helmfile apply
This command installs all defined releases in the correct order with shared values.

3. Verify Deployment
kubectl get pods
kubectl get svc
You should see 10+ services running, including Redis, frontend, and various backend microservices.

⚙️ Features Implemented
Custom Helm charts per service

Environment variables defined via values.yaml

Readiness and liveness probes with configurable timings

Redis deployed via a separate Helm chart and wired to dependent services

LoadBalancer service for public access

Modular Helmfile configuration for clarity and reusability

🧠 What I Learned
How to structure Helm charts for reusable and configurable deployments

Managing configs, and probes across services

Debugging using kubectl logs, describe, and Helm release status

Using Helmfile selectors and overrides for targeted deployment control

📸 Screenshots (Optional)

![image](https://github.com/user-attachments/assets/e94b03c4-e26b-4100-9c47-8673785a90c9)
![image](https://github.com/user-attachments/assets/7a68fffb-9363-462b-9c5a-be2d353e6a1a)
![image](https://github.com/user-attachments/assets/20264b84-d9c1-4761-a69d-702b8638e965)


🔚 Conclusion
This project helped build a deeper understanding of real-world Kubernetes workflows using Helm and Helmfile, and laid a foundation for deploying more complex infrastructure with confidence.


📄 License
MIT — feel free to fork, learn, and modify.

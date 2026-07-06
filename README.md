# GitOps with ArgoCD, Kustomize and Kubernetes

A GitOps implementation demonstrating how to manage Kubernetes deployments using **ArgoCD**, **Kustomize**, and **Kind**. This repository serves as the **single source of truth** for the Kubernetes cluster, containing all deployment manifests, environment overlays, and GitOps configuration.

The application source code is maintained separately in the **aiops-gitops-playbook** repository, while this repository is responsible for managing the desired state of the Kubernetes environment.

## Architecture

```text
Application Repository
(aiops-gitops-playbook)
          │
          ▼
 Build Container Image
          │
          ▼
Update Kubernetes Manifests
          │
          ▼
GitOps Repository
(aiops-gitops)
          │
          ▼
      ArgoCD
          │
          ▼
 Kubernetes Cluster
      (Kind)
```

## Repository Structure

```text
.
├── apps/
│   └── aiops-playbook/
│       ├── base/
│       └── overlays/
│           ├── dev/
│           └── prod/
│
├── argocd/
│
└── clusters/
    ├── dev/
    └── prod/
```

## Tech Stack

- Kubernetes
- Kind
- ArgoCD
- Kustomize
- GitHub
- YAML

## Features

- Declarative Kubernetes deployments
- Git as the single source of truth
- Continuous reconciliation with ArgoCD
- Environment-specific configuration using Kustomize overlays
- Separation of application code and deployment configuration
- Local Kubernetes development with Kind

## Related Repository

**Application Source Code**

🔗 https://github.com/AdahMilly/aiops-gitops-playbook

## Learn More

I documented the architecture, implementation, and design decisions behind this project in a detailed technical article on LinkedIn.

---

> **GitOps Principle:** *Git defines the desired state. ArgoCD continuously reconciles the cluster to match it.*
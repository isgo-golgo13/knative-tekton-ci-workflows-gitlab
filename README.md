# Knative Tekton CI with GitLab and Hashicorp Vault Operator Workflows
GitLab Triggered Knative Tekton In-K8s Cluster CI Pipeline for Go App (Containerize, Aquasec Trivy NIST 800-53 CVE Scan).

The following Kubernetes services are part of this architectural workflow.

- Hashicorp Vault Kubernetes Operator
- External Secrets (Kubernetes) Operator
- Tekton Knative Operator for Parallel Workflows (used for CI and CD)

The required workflow result will provide a coordination of Hashicorp Vault Kubernetes Operator to serve as the
cloud-agnostic Kubernetes-Native (In-Cluster) `Secrets` store. The secret credentials required for Tekton to reference

## Prerequistes

- Kubernetes Cluster
- Helm


## Installation w/ out ArgoCD or FluxCD

The follow workflow is required to configure Tekton and Tetkon Pipeline with GitLab.

- Install (Provision) Kubernetes Cluster
- Install (Provision) Tekton Operator to Kubernetes Cluster
- Install (Provision) Hashicorp Vault Kubernetes Operator to the Kubernetes Cluster
- Configure Hashicorp Vault Kubernetes Operator Auto-Unsealing Workflow (Kubernetes Job)
- Install Kubernetes External Secrets Operator (ESO) and Register ESO w/ Hashicorp Vault
- Configure Kubernetes External Secrets Operator to Pull DockerHub Credentials
- Provision Tekton RBAC Configuration for Kubernetes Cluster and Tekton Namespace
- Provision GitLab WebHook to Trigger Tetkton CI Pipeline w/ Tekton Triggers

# Homelab Kubernetes GitOps Repo

This repository defines a GitOps-driven Kubernetes homelab using [Flux](https://fluxcd.io/), structured around a multi-environment layout with Kustomize. It manages self-hosted applications, infrastructure controllers, and monitoring with Prometheus and Grafana.

## Stack Overview

**GitOps Tooling**
- [Flux](https://fluxcd.io/) — declarative GitOps deployment
- [Renovate](https://github.com/renovatebot/renovate) — automated dependency updates

**Applications**
- [Audiobookshelf](https://www.audiobookshelf.org/)
- [Linkding](https://github.com/sissbruecker/linkding)

**Monitoring**
- [kube-prometheus-stack](https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack)
- Grafana served over TLS

# Secrets Management
Secrets are encrypted with SOPS using Age (public age.agekey present in repo). Unencrypted secrets are never be committed and are

Secrets are typically stored under apps/staging/*/*.yaml 

# Monitoring Setup
Uses kube-prometheus-stack to deploy Prometheus, Alertmanager, and Grafana


# To-Do
Host a few more apps

Roll a Data Lakehouse

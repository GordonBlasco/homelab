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

# Web Exposure via Cloudflare Tunnels
This homelab stack uses Cloudflare Tunnels to securely expose internal services to the web without opening any inbound firewall ports.

Tunnel manifests live under:

```bash
apps/staging/<app>/cloudflare.yaml
apps/staging/<app>/cloudflare-secret.yaml
```
These configure the container to forward internal services (e.g., audiobookshelf, linkding) to a public domain via my Cloudflare account.

Secrets contain the tunnelToken required for authentication.

# Secrets Management
Secrets are encrypted with SOPS using Age (public age.agekey present in repo). Unencrypted secrets are never be committed are typically stored in encrypted form under apps/staging/*/*.yaml.

# Monitoring Setup
Uses kube-prometheus-stack to deploy Prometheus, Alertmanager, and Grafana


# To-Do
- Host a few more apps.
- Expose something publically that is fun to interact with.
- Roll a Data Lakehouse.

# Architecture Overview

## System Design

This homelab implements a modern data platform on Kubernetes with the following layers:

### Infrastructure Layer
- Kubernetes cluster
- Flux CD for GitOps
- Rook/Ceph for storage
- Networking and ingress

### Data Layer
- Object storage (lakehouse)
- Databases
- Data catalog
- Processing engines

### Application Layer
- Development tools (VS Code Server)
- Authentication (Keycloak)
- User applications

### Observability Layer
- Metrics collection
- Logging
- Alerting

## Design Principles

- **GitOps**: All configuration in Git
- **Declarative**: Infrastructure as code
- **Scalable**: Designed to grow
- **Observable**: Full visibility into system state

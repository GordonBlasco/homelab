# Troubleshooting

## Flux Not Syncing

Check Flux status and logs:
```bash
flux get sources git
flux logs
```

## Pod Not Starting

Check pod status and events:
```bash
kubectl describe pod <pod-name> -n <namespace>
kubectl logs <pod-name> -n <namespace>
```

## Storage Issues

Check Rook/Ceph status:
```bash
kubectl get cephcluster -n rook-ceph
kubectl get cephblockpool -n rook-ceph
```

## Network Issues

Check ingress and services:
```bash
kubectl get ingress -A
kubectl get svc -A
```

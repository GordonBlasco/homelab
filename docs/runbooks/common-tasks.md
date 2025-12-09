# Common Tasks

## Deploying a New Application

1. Create manifests in `apps/base/<app-name>/`
2. Create kustomization overlay in `apps/staging/<app-name>/`
3. Reference in `clusters/staging/apps.yaml`
4. Commit and push - Flux will deploy

## Updating an Application

1. Update the manifest or kustomization
2. Commit and push
3. Monitor with `flux get kustomizations`

## Checking Flux Status

```bash
flux get kustomizations
flux get helmreleases
flux logs
```

## Accessing Logs

```bash
kubectl logs -n <namespace> <pod-name>
```

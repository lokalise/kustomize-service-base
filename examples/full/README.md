## Full example

```
# Build the YAML manifests
$ kustomize build overlays/dev
```

### Deploy

```
# Create the ArgoCD application
$ kubectl apply -f application.yaml
```

ArgoCD will compile the manifests with `kustomize` and apply them to the cluster.

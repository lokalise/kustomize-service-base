# Common kustomize manifests

## Usage

Check the `examples` directory: https://github.com/lokalise/kustomize-service-base/tree/main/examples/full

## Organization

Manifests are groupped in directories, under `manifests/`. Groups can be included
into your `kustomize.yaml` files, as a `resource`:

```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

resources:
- github.com/lokalise/kustomize-service-base/manifests/deployment
- github.com/lokalise/kustomize-service-base/manifests/ingress
- github.com/lokalise/kustomize-service-base/manifests/hpa
- github.com/lokalise/kustomize-service-base/manifests/pdb
```

Group | Kubernetes Resources
--- | ---
deployment | `Deployment`<br>`Service`<br>`ServiceAccount`<br>`ServiceMonitor`
ingress | `Ingress`
hpa | `HorizontalPodAutoscaler`
pdb | `PodDisruptionBudget`

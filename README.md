# Common kustomize manifests

## Contributing

Use conventional commits, when making changes to assure a good changelog and
versioning: https://www.conventionalcommits.org/en/v1.0.0/#summary

---

The commit contains the following structural elements, to communicate intent to the consumers of your library:

  fix: a commit of the type fix patches a bug in your codebase (this correlates with PATCH in Semantic Versioning).
  Example: `fix: Add default value to field`

  feat: a commit of the type feat introduces a new feature to the codebase (this correlates with MINOR in Semantic Versioning).
  Example: `feat: Introduce new component`

  BREAKING CHANGE: a commit that has a footer BREAKING CHANGE:, or appends a ! after the type/scope, introduces a breaking API change (correlating with MAJOR in Semantic Versioning). A BREAKING CHANGE can be part of commits of any type.
  Example: `BREAKING CHANGE: Restructure`

---

## Usage

Check the `examples` directory: https://github.com/lokalise/kustomize-service-base/tree/main/examples/full

## Organization

Manifests are groupped in directories, under `manifests/`. Groups can be included
into your `kustomize.yaml` files, as a `resource`:

```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

resources:
- github.com/lokalise/kustomize-service-base/manifests/rollout
- github.com/lokalise/kustomize-service-base/manifests/ingress
- github.com/lokalise/kustomize-service-base/manifests/ingress-internal
- github.com/lokalise/kustomize-service-base/manifests/job
- github.com/lokalise/kustomize-service-base/manifests/slo
```

Group | Kubernetes Resources | Description
--- | --- | ---
rollout | `Rollout`<br>`Service`<br>`ServiceAccount`<br>`ServiceMonitor`<br>`ScaledObject`<br>`PodDisruptionBudget`<br>`NetworkPolicy` | All required components for an application, following best practices. No associated ingress.
ingress | `Ingress` | Public Nginx ingress (routable from the Internet).
ingress-internal | `Ingress` | Private Nginx ingress (routable only from within the clusters and Tailscale). Creates 2 ingresses: application, application preview (argo rollout b/g).
job | `Job`, `Secret` | Job which starts in the `PreSync` ArgoCD phase for executing tasks like DB migrations. Runs commands in the app container.
slo | `PrometheusServiceLevel` | [Sloth SLO specification](https://sloth.dev/examples/default/getting-started/) from which `PrometheusRule` resources are generated by the `sloth` controller.


To remove a resource from a group, for example if you don't need a `ServiceAccount` in the `rollout` group,
do the following on the "client-side":

```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

resources:
- github.com/lokalise/kustomize-service-base/manifests/rollout

patchesStrategicMerge:
  # Exclude unneded resources from base
  - |-
    $patch: delete
    apiVersion: v1
    kind: ServiceAccount
    metadata:
      name: serviceaccount
```

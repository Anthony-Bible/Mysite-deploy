# Mysite-deploy

GitOps deploy repo for [Mysite](https://github.com/Anthony-Bible/Mysite).

The `Mysite` repo's GitHub Actions workflow renders K8s manifests from
`k8s/*.yaml` (substituting `%{VERSION}`, `%{PHASE}`, `%{MAIN_IMAGE_SHA}`)
and commits the result here:

- `dev/mysite.yaml` — on every `master` push (image tagged with short SHA)
- `prod/mysite.yaml` — on every `v*` tag push (image tagged with the tag)

ArgoCD watches this repo and applies changes to the cluster.

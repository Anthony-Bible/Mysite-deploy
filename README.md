# Mysite-deploy

GitOps deploy repo for [Mysite](https://github.com/Anthony-Bible/Mysite).

The `Mysite` repo's GitHub Actions workflow renders `k8s/*.yaml`
(substituting `%{VERSION}` and `%{MAIN_IMAGE_SHA}`) and commits the result
to `mysite.yaml` here on every `master` push and `v*` tag.

ArgoCD watches this repo and applies changes to the cluster.

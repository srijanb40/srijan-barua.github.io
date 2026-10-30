---
layout: post
title: "GitOps with Argo CD: patterns that scale"
---

# GitOps with Argo CD: patterns that scale

Git is the source of truth; Argo CD reconciles the cluster to match it.

## App-of-apps
One root `Application` points to a folder of child `Application` manifests, so a new cluster bootstraps with a single apply.

## Environments
Use Kustomize overlays (`base/`, `overlays/dev|stage|prod`) and promote by pull request, not by editing the cluster.

## Safe sync policy
```yaml
syncPolicy:
  automated:
    prune: true
    selfHeal: true
  syncOptions: [CreateNamespace=true]
```
Use manual sync with sync windows for production if your change process requires approval.

## Secrets
Never commit plain secrets. Use Sealed Secrets, External Secrets or SOPS.

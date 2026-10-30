---
layout: post
title: "Hardening Kubernetes: a practical checklist"
---

# Hardening Kubernetes: a practical checklist

## Cluster
- Enable audit logging and restrict API server access.
- Run the CIS benchmark with `kube-bench` and track findings.

## Workloads
- Enforce Pod Security Standards (restricted) per namespace.
- Block privileged pods, host paths and `latest` tags with OPA Gatekeeper constraints.
- Set resource requests, limits, and `readOnlyRootFilesystem`.

## Network and identity
- Default-deny `NetworkPolicy`, then allow explicitly.
- Least-privilege RBAC; review `cluster-admin` bindings regularly.

## Supply chain and runtime
- Scan images in CI and again in the registry; sign images.
- Use runtime detection (Falco or Sysdig) and route alerts to on-call.

Treat vulnerabilities as a workflow: triage, owner, deadline, verification.

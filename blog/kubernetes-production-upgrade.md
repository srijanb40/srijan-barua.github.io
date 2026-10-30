---
layout: post
title: "Upgrading a production Kubernetes cluster safely"
---

# Upgrading a production Kubernetes cluster safely

Upgrades go wrong when they are treated as a single event. Treat them as a rehearsed procedure.

## Before
- Read the release notes and the deprecated API list; scan manifests with `kubent` or `pluto`.
- Take an etcd snapshot and confirm a restore works in a lab.
- Check PodDisruptionBudgets and spare capacity so drains can finish.

## During
1. Upgrade the control plane one node at a time.
2. Upgrade workers in small batches: `kubectl cordon`, `kubectl drain --ignore-daemonsets --delete-emptydir-data`, upgrade, `kubectl uncordon`.
3. Watch error rates and latency on your dashboards between batches.

## After
- Verify node versions, CNI, CSI, ingress and service mesh health.
- Record what surprised you in the runbook.

**Rule of thumb:** if you cannot roll back, you are not ready to upgrade.

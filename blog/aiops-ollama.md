---
layout: post
title: "AIOps with a local LLM: alert triage with Ollama"
---

# AIOps with a local LLM: alert triage with Ollama

Goal: reduce time-to-context when an alert fires, without sending operational data outside your network.

## Flow
1. Alertmanager sends a webhook to n8n.
2. n8n gathers context: recent logs, pod status, recent deploys.
3. The context is sent to a model served by Ollama.
4. The summary and suggested checks are posted to chat or the ticket.

## Calling the model
```bash
curl http://localhost:11434/api/generate -d '{"model":"llama3.1","prompt":"Summarize this alert and list three checks: ...","stream":false}'
```

## Guardrails
- Read-only access: the assistant suggests, humans act.
- Redact secrets and personal data before prompting.
- Log prompts and outputs for review.

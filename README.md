# AChA GitHub Defaults

This repository supplies Australian Christian Arts' default GitHub issue forms,
pull request template, and issue-operations guidance for repositories in the
`AustralianChristianArts` organisation.

## What This Configures

- Structured issue intake for bugs, automation failures, ops tasks, decisions,
  and documentation/content changes.
- A pull request checklist that requires verification, deployment notes, and
  explicit call-outs for approval-gated work.
- A shared label vocabulary for triage, priority, issue type, domain, and status.

## Automation Shape

GitHub should stay useful on its own, even when external automation is offline.
The first layer is therefore GitHub-native: issue forms, labels, PR templates,
and Actions failure issues.

The second layer can be wired through self-hosted n8n:

1. GitHub sends organisation or repository webhook events to n8n.
2. n8n validates the GitHub webhook signature.
3. n8n applies labels, opens follow-up issues, and notifies Team AI or the
   Coolify-hosted API server when the event needs operational attention.
4. n8n queues approval-gated work instead of performing it automatically.

No credentials or webhook secrets belong in this public repository.


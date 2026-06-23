# Veyron — Community

> **Kubernetes-native VM command center — Rust, KubeVirt, 44 OS templates, 40+ dashboard pages**

Public issue tracker and community feedback space for **Veyron** by [Zyvor AI Labs](https://zyvor.dev).

The source code is maintained in a private repository. This repo is for:
- Bug reports
- Feature requests
- UX feedback
- Documentation gaps
- Questions and discussion

---

## Key features

- Declarative VM builder — 44 OS templates, 8 resource profiles
- Mission Control web dashboard — 40+ specialized pages
- CLI · TUI · REST API (49 routes)
- VeyronVM CRD + Go operator for GitOps
- Browser VNC console — direct K8s WebSocket
- Multi-VM blueprints: LAMP, K8s, 3-tier, CI/CD
- VeyronPolicy CRDs with CEL deny rules
- Terraform provider

---

## Installation

Veyron runs on any Kubernetes cluster with KubeVirt installed.

**Helm:**
```bash
helm repo add hypersdk https://charts.hypersdk.dev
helm install veyron hypersdk/veyron -n veyron-system --create-namespace
```

**CLI (standalone):**
```bash
# Download the latest release binary
curl -fsSL https://releases.hypersdk.dev/veyron/install.sh | bash

# Create a VM from template
veyron create --template ubuntu-22.04 --name web-01

# Deploy a blueprint stack
veyron blueprint deploy lamp --namespace dev

# Web dashboard + API
veyron serve  # → https://localhost:8080
```

**Requirements:** Kubernetes 1.28+, KubeVirt installed, 2 GB RAM for the control plane

---

## Report a bug

[Open a Bug Report →](../../issues/new?template=bug_report.yml)

Include: what you did, what happened, what you expected, your environment, and screenshots/logs (redact secrets).

## Request a feature

[Open a Feature Request →](../../issues/new?template=feature_request.yml)

## UX feedback

[Open a UX Feedback →](../../issues/new?template=ux_feedback.yml)

## Ask a question

Use [GitHub Discussions](../../discussions) for open-ended questions, ideas, and roadmap conversations.

---

## Security

**Do not report security vulnerabilities publicly.**

Email **security@zyvor.dev** — see [SECURITY.md](SECURITY.md).

---

## Do not post

- Source code or internal configuration
- API tokens, license keys, or credentials  
- Private logs with sensitive data
- Security vulnerabilities (email security@zyvor.dev)

---

Maintained by [Zyvor AI Labs](https://zyvor.dev)

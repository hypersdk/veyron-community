---
> 🚀 **Trial v0.30.0 is live!** The latest release is available for trial today — [get started in 5 minutes →](#try-v030-in-5-minutes)

# Veyron — Community

> **Kubernetes-native VM command center — Rust, KubeVirt, 44 OS templates, 40+ dashboard pages.**

![Version](https://img.shields.io/badge/version-v0.30.0-blue) ![Discussions](https://img.shields.io/github/discussions/hypersdk/veyron-community) ![Issues](https://img.shields.io/github/issues/hypersdk/veyron-community) ![License](https://img.shields.io/badge/license-Proprietary-red)

Public issue tracker and community feedback space for **Veyron** by [Zyvor AI Labs](https://zyvor.dev).
The source code is maintained in a private repository. This repo is for bug reports, feature requests, UX feedback, and community discussion.

---

## What's new in v0.30

- Live VM migration is now GA — migrate running VMs between nodes from the UI
- Snapshot restore directly from the Mission Control dashboard
- ARM64 node support — Veyron CLI and operator run natively on Apple Silicon and Ampere
- Terraform provider v0.30 — manage VMs as code with full state import
- Blueprint stacks: added 6 new templates (Redis cluster, Kafka, Postgres HA)

---

## Why Veyron

| Problem | Veyron answer |
|---------|--------------|
| KubeVirt YAML is verbose and error-prone | Templates, validation, blueprints — create VMs in seconds |
| virtctl gives a single VM, not a fleet | Mission Control manages your entire VM estate from one dashboard |
| GitOps needs CR-native VM definitions | VeyronVM CRD + operator — commit VMs to git, operator reconciles |
| Browser VNC through kubectl port-forward drops | Direct K8s WebSocket VNC — stable, persistent, shareable URL |
| Policy violations slip through at scale | VeyronPolicy CRDs with CEL deny rules — enforce before apply |

---

## Architecture

```
┌──────────────────────────────────────────────────────────────┐
│  Surfaces     CLI · TUI · Web dashboard · REST API (49 routes)│
├──────────────────────────────────────────────────────────────┤
│  GitOps       VeyronVM CRD · Go operator · Helm charts       │
├──────────────────────────────────────────────────────────────┤
│  KubeVirt     VirtualMachine lifecycle · snapshots · migrate │
└──────────────────────────────────────────────────────────────┘
```

---

## Try v0.30 in 5 minutes

```bash
helm repo add hypersdk https://charts.hypersdk.dev
helm install veyron hypersdk/veyron --version 0.30.0 \
  -n veyron-system --create-namespace
```

Access the dashboard:
```bash
kubectl port-forward svc/veyron-ui 8080:80 -n veyron-system
# → http://localhost:8080
```

Create your first VM:
```bash
veyron create --template ubuntu-22.04 --name my-first-vm
```

**Requirements:** Kubernetes 1.28+, KubeVirt installed, 2 GB RAM for the Veyron control plane

---

## Report a bug

[Open a Bug Report →](../../issues/new?template=bug_report.yml)

Include: what you did, what happened, what you expected, your environment, screenshots or logs (redact secrets).

## Request a feature

[Open a Feature Request →](../../issues/new?template=feature_request.yml)

## UX feedback

[Open a UX Report →](../../issues/new?template=ux_feedback.yml)

## Ask a question

Use [GitHub Discussions](../../discussions) for open-ended questions, ideas, and roadmap conversations.

---

## Security

**Do not report security vulnerabilities publicly.**
Email **security@zyvor.dev** — see [SECURITY.md](SECURITY.md).

---

## Do not post

- Source code, internal configs, or architecture details
- API tokens, license keys, or credentials
- Private logs with sensitive data
- Security vulnerabilities — email security@zyvor.dev instead

---

## Join the community

⭐ [Star this repo](https://github.com/hypersdk/veyron-community) · 💬 [Open a Discussion](https://github.com/hypersdk/veyron-community/discussions) · 🐛 [Report a Bug](../../issues/new?template=bug_report.yml) · 📧 [hello@zyvor.dev](mailto:hello@zyvor.dev)

Maintained by [Zyvor AI Labs](https://zyvor.dev)

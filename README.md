# 🔐 secure-ci-cd

A collection of tools, checks, and hardening guides for securing modern CI/CD pipelines. This repo is designed for engineers, DevSecOps practitioners, and security-minded developers who want to prevent supply chain attacks, secrets leakage, and untrusted code execution in their delivery pipelines.

> 🎯 CI/CD is the lifeblood of modern infrastructure — and often the weakest link. This repo helps you lock it down.

## 📁 Repository Structure

| Folder             | Description                                                      |
|--------------------|------------------------------------------------------------------|
| `github-actions/`   | Hardened GitHub Actions workflows for linting, secrets scanning, and signing |
| `gitlab-ci/`        | GitLab CI examples with secure runners, SBOMs, and image scanning |
| `pipeline-attacks/` | Simulated examples of common CI/CD misconfigurations and abuse   |
| `hardening-guides/` | Secure defaults for runners, workflows, credentials, and audit logging |
| `tools/`            | Wrappers around tools like TruffleHog, Snyk, Syft, and Cosign    |

## 🧱 What’s Included

### ✅ GitHub Actions Security Workflows
- `secret-scanning.yml` – Runs TruffleHog and GitLeaks on every push
- `sbom-generation.yml` – Builds SBOMs with Syft, scans with Grype
- `signed-artifacts.yml` – Uses Cosign to sign and verify container builds

### ✅ GitLab CI Security Pipelines
- `scan-container.gitlab-ci.yml` – Uses `snyk` and `grype` to scan image builds
- `enforce-2fa.md` – Organizational policy tips to harden GitLab access

### ⚠️ CI/CD Attack Simulations
- `token-leak-sim.md` – How secrets leak via logs and environment variables
- `unsafe-default-branch.md` – Risks of direct pushes and auto-deploys from `main`
- `runner-abuse.md` – What happens when your runner is exposed or misconfigured

### 🛡️ Hardening Guides
- `github-hardening.md` – Secure workflows, required reviewers, PR branch protection
- `runner-security.md` – Secure self-hosted runners in GitHub or GitLab
- `audit-logging.md` – Enable and monitor CI audit events

### 🧰 Tool Wrappers
- `trufflehog-wrapper.py` – Custom wrapper for secrets scanning
- `cosign-verify.sh` – Signs and verifies Docker images
- `snyk-scan.sh` – CLI wrapper to scan projects before merge

## 💡 Use Cases

- Lock down default GitHub Actions and GitLab CI runners
- Prevent secrets from leaking through pushes, PRs, or build logs
- Automate SBOM creation and vulnerability scanning
- Learn and simulate common CI/CD pipeline attack vectors
- Build security directly into DevOps workflows

## 🧬 Philosophy

> CI/CD is infrastructure. It’s also a privileged attack surface.  
> **Security must be built into the automation, not tacked on.**

This repo reflects the belief that:
- Secure pipelines are reproducible pipelines
- Developers deserve safe defaults
- Pull requests should be a security boundary
- Audit logs are just as important as build logs

## ⚙️ Requirements

- GitHub or GitLab account
- Docker (for SBOM scans)
- Python 3.8+ (for CLI tools)
- CLI installs: `trufflehog`, `cosign`, `syft`, `grype`, `snyk` (install docs included)

## 🧠 Next Steps

- [ ] Add CI/CD threat modeling templates
- [ ] Build an end-to-end secure pipeline with SBOM + signature verification
- [ ] Expand to include Jenkins and CircleCI
- [ ] Add GitHub Actions to test secrets, diffs, and SBOMs per push


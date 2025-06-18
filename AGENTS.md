---
name: "container-images"
description: "Nix-based Docker images built with GitHub Actions"
category: "DevOps / Container Build"
author: "ACME OSS Team"
tags: ["nix", "docker", "github-actions"]
lastUpdated: "2025-06-18"
---

# AGENTS.md – Contract for Autonomous Coding Agents

> **If you are an LLM-powered agent** (Copilot coding-agent, ChatGPT Codex, Devin, Zencoder, etc.) **you MUST follow every rule below for every file you touch**. Violations will cause CI to fail and your PR to be closed.

---

## 0. Scope & Precedence
| Level | File path | Applies to | Priority |
|-------|-----------|-----------|----------|
| 1 | `system/user prompt` | Current session | 🥇 |
| 2 | Nearest `AGENTS.md` | Folder subtree | 🥈 |
| 3 | Repo-root `AGENTS.md` | Whole repo | 🥉 |
| 4 | `~/.codex/AGENTS.md` or `~/.codex/instructions.md` | Global user prefs | 🏅 |

When conflicts occur, **higher priority wins**.

---

## 1. Project Capsule
This repository stores Docker images built with Nix flakes. GitHub Actions build and publish these images for multi-platform use.

---

## 2. Directory Contract
<small>(Update this table whenever paths change.)</small>

| Path | Intent | Touch policy |
|------|--------|--------------|
| `/hummingbot-postgres` | Docker context for Hummingbot image | **Modifiable** |
| `/.github` | Workflow and Renovate config | Keep CI passing |
| `/flake.nix` | Nix flake definition | Keep valid |
| `/README.md` | Project overview | Keep informative |

---

## 3. Tech Stack & Runtime
| Tool | Version | Install |
|------|---------|---------|
| Nix | `nixos-unstable` | <https://nixos.org/download.html> |
| Docker | multi-platform buildx | <https://docs.docker.com/get-docker/> |
| TODO: additional tools |  |  |

---

## 4. Coding Conventions
* **Language**: Nix and Dockerfiles.
* **Style**: `treefmt` with `alejandra` for Nix and `yamlfmt` for YAML.
* **Comments**: Document major build steps and unusual configuration.

---

## 5. Testing Strategy
* TODO: define container tests or smoke checks.

---

## 6. Build & Run Recipes
```bash
# format all sourcesnix run .#fmt
# build the hummingbot image
nix build .#hummingbot-postgres
```

Once drafted, run all programmatic checks locally; fix any issues before committing `AGENTS.md` and opening the PR.

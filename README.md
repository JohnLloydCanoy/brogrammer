# ⚡ Workflow & Skill Hub (`workflow-skill`)

> A curated, modular collection of agent **skills**, **rules**, and **workflows** designed for developers and AI coding agents (Antigravity, Claude Code, Cursor, Codex, and more).

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Agents Supported](https://img.shields.io/badge/Agents-Antigravity%20%7C%20Claude%20%7C%20Cursor-orange.svg)](#supported-ecosystems)

---

## 🎯 Vision & Purpose

Modern AI coding agents become exponentially more useful when equipped with reusable domain knowledge, structured execution patterns, and consistent operational rules. 

`workflow-skill` serves as a universal, community-driven catalog where anyone can:
- 🧩 **Discover & Adopt Skills**: Specialized procedures packaged in clean, portable `SKILL.md` files.
- 📐 **Standardize Rules**: Project and agent governance rules for code quality, architectural integrity, and safety boundaries.
- 🔄 **Automate Workflows**: Step-by-step orchestrations for complex engineering rituals (refactoring, PR review pipelines, bug triage, releases).

---

## 📁 Repository Structure

```plaintext
workflow-skill/
├── .agent/                  # Workspace-level agent configurations & overrides
├── rules/                   # General and framework-specific rulebooks
│   ├── code-style/          # Linting, naming conventions, formatting
│   ├── safety-and-git/      # Commit guidelines, branch protection, sandboxing
│   └── architecture/        # Design principles, testing strategies
├── skills/                  # Domain-specific modular agent skills
│   ├── gemini/              # Gemini & Antigravity skills & sidecars
│   ├── claude/              # Claude Code tailored utilities & prompts
│   ├── gen/                 # General-purpose productivity skills
│   │   └── chief-of-staff/  # Project management, task planning, delegation
│   └── [category]/          # Categorized skill folders containing SKILL.md
├── workflows/               # Multi-step playbooks and pipeline orchestrations
│   ├── incident-triage/     # Root-cause analysis & post-mortem workflows
│   └── feature-delivery/    # Spec-to-ship structured lifecycle
└── README.md
```

---

## 🚀 Quick Start & Usage

### Method 1: Direct Copy or Symlink to Your Agent Environment

#### For Antigravity Agents
Copy or symlink desired skills to your Antigravity skills directory:
```bash
# Copy a skill into your global Antigravity skills directory
cp -r skills/gen/chief-of-staff ~/.gemini/antigravity-cli/skills/

# Or symlink directly for real-time updates (Linux/macOS)
ln -s "$(pwd)/skills/gen/chief-of-staff" ~/.gemini/antigravity-cli/skills/chief-of-staff

# Or symlink on Windows (PowerShell Run as Admin)
New-Item -ItemType SymbolicLink -Path "$HOME\.gemini\antigravity-cli\skills\chief-of-staff" -Target ".\skills\gen\chief-of-staff"
```

#### For Claude Code / Cursor / Windsurf
Import rules and workflows into your project root:
```bash
# Add rules to your active project
cp rules/safety-and-git/git-conventions.md /path/to/project/.cursorrules
# or include into CLAUDE.md / AGENTS.md
```

### Method 2: Git Submodule
Include this entire repository into your existing project as a submodule:
```bash
git submodule add https://github.com/JohnLloydCanoy/workflow-skill.git .agent/hub
```

---

## 📚 Directory Catalogs

### 🧩 Skills (`/skills`)
| Skill / Path | Ecosystem / Scope | Description | Status |
| :--- | :--- | :--- | :--- |
| [`gen/chief-of-staff`](skills/gen/chief-of-staff/SKILL.md) | General Productivity | Orchestrates tasks, plans sprints, and acts as executive partner | `Draft` |
| [`gemini`](skills/gemini/) | Gemini / Antigravity | Antigravity CLI, sidecars, and subagent orchestration skills | `In Progress` |
| [`claude`](skills/claude/) | Claude Code | Tailored utilities, hooks, and prompts for Claude Code | `In Progress` |

### 📐 Rules (`/rules`)
| Rule | Scope | Description |
| :--- | :--- | :--- |
| `git-conventions` | Version Control | Standardized conventional commits, branch hygiene, and PR drafts |
| `clean-code-principles` | Architecture | Guardrails for modularity, single-responsibility, and documentation |

### 🔄 Workflows (`/workflows`)
| Workflow | Target Outcome | Description |
| :--- | :--- | :--- |
| `feature-lifecycle` | Idea to PR | Requirements breakdown &rarr; Plan &rarr; Subagent execution &rarr; Verification |
| `codebase-deep-dive` | Onboarding | Automated mapping of architecture, boundaries, and dependencies |

---

## 🛠️ Contribution Guidelines

We welcome community contributions! Whether you have a single prompt optimization, a battle-tested rule, or an entire multi-agent skill:

### 1. Adding a New Skill
Create a folder under `skills/<skill-name>/` containing a `SKILL.md`:

```markdown
---
name: your-skill-name
description: A clear, 1-2 sentence description of when and why to activate this skill.
---

# Your Skill Name

## Overview
Brief explanation of what this skill does and prerequisite tools.

## Instructions & Steps
1. First step...
2. Next action...

## Examples & References
Provide input/output examples or prompt triggers.
```

### 2. Adding a Rule
- Place your rule under the appropriate subfolder in `rules/`.
- Ensure it is actionable and unambiguous for both LLMs and human contributors.

### 3. Pull Request Checklist
- [ ] Added `SKILL.md` with standard YAML frontmatter (`name`, `description`).
- [ ] Tested with at least one agent (Antigravity, Claude Code, Cursor, etc.).
- [ ] Updated the index tables in this `README.md`.
- [ ] No hardcoded secrets, private tokens, or proprietary code.

---

## 🤝 Supported Ecosystems

- [Google Antigravity CLI](https://github.com)
- [Anthropic Claude Code](https://docs.anthropic.com/en/docs/claude-code)
- [Cursor IDE](https://cursor.com)
- [Windsurf IDE](https://codeium.com/windsurf)
- [GitHub Copilot / Workspace](https://github.com/features/copilot)

---

## 📄 License

This repository is distributed under the [MIT License](LICENSE). Feel free to use, adapt, and distribute these skills in personal or commercial projects.

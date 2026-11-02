# brogrammer

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](#contributing)
[![Supported Agents](https://img.shields.io/badge/Agents-Antigravity%20%7C%20Claude%20%7C%20Cursor-555.svg)](#usage)

A shared repository of modular skills, rules, and workflows for AI coding assistants (such as Antigravity, Claude Code, and Cursor).

## Overview

This repository centralizes reusable components for AI-assisted development:
- **Skills**: Task-specific instructions defined in `SKILL.md` files.
- **Rules**: Coding standards, Git conventions, and operational constraints.
- **Workflows**: Multi-step procedures for development, debugging, and releases.

## Repository Structure

```text
brogrammer/
├── .agent/                  # Workspace configurations
├── rules/                   # Project and environment rules
│   ├── code-style/          # Formatting and language-specific standards
│   ├── safety-and-git/      # Version control policies and conventions
│   ├── architecture/        # Design and testing patterns
│   └── ui/                  # Interface design standards and constraints
├── skills/                  # Modular agent skills
│   ├── claude/              # Claude Code specific configurations
│   ├── gemini/              # Gemini and Antigravity skills
│   └── gen/                 # General-purpose skills
│       └── chief-of-staff/  # Project management and planning
├── workflows/               # Multi-step procedures
└── README.md
```

## Usage

### 1. Direct Copy or Symlink

#### Antigravity / Gemini CLI
Copy or symlink the required skill into your local skills directory:

**Linux / macOS**
```bash
ln -s "$(pwd)/skills/gen/chief-of-staff" ~/.gemini/antigravity-cli/skills/chief-of-staff
```

**Windows (PowerShell as Administrator)**
```powershell
New-Item -ItemType SymbolicLink -Path "$HOME\.gemini\antigravity-cli\skills\chief-of-staff" -Target ".\skills\gen\chief-of-staff"
```

#### Claude Code / Cursor / Windsurf
Copy relevant rules directly into your project root:
```bash
cp rules/safety-and-git/git-conventions.md /path/to/project/.cursorrules
```

### 2. Git Submodule
To track this repository inside an existing project:
```bash
git submodule add https://github.com/JohnLloydCanoy/brogrammer.git .agent/hub
```

## Catalog

### Skills (`skills/`)
| Skill | Target | Description | Status |
| :--- | :--- | :--- | :--- |
| [`gen/chief-of-staff`](skills/gen/chief-of-staff/SKILL.md) | General | Task decomposition, planning, and tracking | In Progress |
| [`gemini`](skills/gemini/) | Gemini / Antigravity | Antigravity CLI and subagent configurations | In Progress |
| [`claude`](skills/claude/) | Claude Code | Prompts and tool definitions for Claude Code | In Progress |

### Rules (`rules/`)
| Rule | Scope | Description |
| :--- | :--- | :--- |
| [`ui-rules`](rules/ui/1.%20ui.md) | UI / Visual | Anti-AI slop visual design rules, solid colors, and anti-clichés |
| [`ux-rules`](rules/ui/2.%20ux.md) | UX / Interaction | Anti-AI slop interaction design, state resilience, and accessibility |
| `git-conventions` | Git | Commit message formats and branching rules |
| `clean-code-principles` | Code Quality | Architecture boundaries and documentation standards |

### Workflows (`workflows/`)
| Workflow | Description |
| :--- | :--- |
| `feature-lifecycle` | Requirements definition, implementation plan, execution, and verification |
| `codebase-deep-dive` | Repository analysis, architecture mapping, and onboarding |

## Contributing

### Adding a Skill
Create `skills/<category>/<skill-name>/SKILL.md` using the standard format:

```markdown
---
name: skill-name
description: Brief description of what the skill does and when to use it.
---

# Skill Name

## Description
Detailed explanation of scope and prerequisites.

## Instructions
1. Step one.
2. Step two.
```

### Adding a Rule
Place rule definitions as markdown files in the appropriate subdirectory inside `rules/`. Keep rules explicit and testable.

### Pull Requests
1. Ensure `SKILL.md` files include valid YAML frontmatter (`name` and `description`).
2. Do not commit credentials, tokens, or private paths.
3. Update the catalog tables in this file when adding new entries.

## License

MIT

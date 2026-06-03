# CLAUDE.md — Luna1227 AI Stack

@RTK.md

## Setup Overview

This repo is configured with a full AI-augmented Claude Code stack:

### 1. 207 Specialized Agents (`~/.claude/agents/`)
Agency agents covering 12 divisions: Engineering, Marketing, Sales, Finance, Design, Testing, Paid Media, Product, Project Management, Support, Spatial Computing, Game Dev.

**Activation patterns:**
```
# Explicit
Active l'agent Financial Analyst. Mission : ...

# By expertise
Fais-moi [mission] en mode Financial Analyst.
```

**Top agents by use case:**
| Agent | Use case |
|-------|----------|
| `financial-analyst` | ROI, marges, modèles financiers |
| `outbound-strategist` | Cold outreach, séquences multi-canal |
| `deal-strategist` | Qualification MEDDPICC, closing B2B |
| `growth-hacker` | Viral loops, A/B tests, acquisition |
| `email-intelligence-engineer` | Parse emails, décisions en suspens |
| `engineering-backend-architect` | Architecture, API design |
| `engineering-code-reviewer` | Code review systématique |
| `marketing-content-creator` | Contenu, copywriting |
| `seo-specialist` | SEO technique et éditorial |

**Rule:** Maximum 1-2 agents par conversation pour garder le focus.

### 2. RTK — Rust Token Killer
Intercepte automatiquement toutes les commandes Bash, filtre le bruit, économise 60-90% de tokens.

```bash
rtk gain          # Voir les économies réalisées
rtk gain --history  # Historique par commande
rtk discover      # Analyser les opportunités manquées
```

### 3. Best Practices Claude Code (`.claude/best-practice/`)
Documentation de référence sur les subagents, skills, hooks, MCP, settings.

**Docs disponibles :**
- `.claude/best-practice/claude-subagents.md` — Frontmatter fields, built-in agents
- `.claude/best-practice/claude-skills.md` — Skills system
- `.claude/best-practice/claude-settings.md` — Configuration hierarchy
- `.claude/best-practice/claude-commands.md` — Slash commands
- `.claude/best-practice/claude-mcp.md` — MCP servers
- `.claude/best-practice/claude-memory.md` — Memory system
- `.claude/best-practice/claude-power-ups.md` — Advanced patterns

## Project `.claude/` Structure

```
.claude/
├── settings.json          # Permissions et config projet
├── agents/                # Agents from best-practice (weather, time, etc.)
├── skills/                # Skills: weather-fetcher, weather-svg-creator, time-skill
└── best-practice/         # Docs de référence Claude Code
```

## Quick Start

```bash
# Voir les agents disponibles
ls ~/.claude/agents/

# Vérifier RTK
rtk --version
rtk gain

# Lancer Claude Code sur ce repo
claude
```

## Tips

1. **Ne pas activer 5 agents en même temps** — max 1-2 par conversation
2. **Customiser les agents** — `nano ~/.claude/agents/financial-analyst.md`
3. **Mettre à jour les agents** — `cd /tmp/agency-agents && git pull && cp agents/*.md ~/.claude/agents/`
4. **RTK analytics** — `rtk gain` après 1h d'utilisation

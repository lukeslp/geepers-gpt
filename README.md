# geepers-gpt

A portable skill pack for GPT-focused CLI workflows.

## What You Get

**Workflow Specialists** — engineering lifecycle skills:
- `scout`, `planner`, `builder`, `testing`, `validator` — project recon → plan → build → test → validate
- `team`, `swarm`, `quality`, `dream` — routing, parallel research, quality audit, dual-model critique
- `humanize`, `publish`, `poet`, `readme`, `doublecheck` — content and publication utilities

**Domain Tools** — specialized knowledge packs:
- `datavis` — D3.js/Chart.js visualization design with color theory and perceptual accuracy
- `data-fetch` — structured retrieval from 15+ authoritative APIs (arXiv, Census, GitHub, NASA, etc.)
- `dream-swarm` — parallel multi-domain research orchestration
- `engineering` — full-stack architecture and code implementation
- `executive`, `finance`, `product` — strategic planning orchestrators
- `server-deploy` — service deployment and Caddy routing
- `mcp-orchestration` — multi-agent Dream Cascade/Swarm coordination
- `git-hygiene-guardian` — repo cleanup and artifact removal

## Repository Layout

- `skills/<skill-name>/SKILL.md`: skill instructions and routing logic
- `skills/<skill-name>/scripts/`: optional helper scripts used by that skill

## Install

Copy one or more skills into your Codex skills directory:

```bash
cp -a skills/<skill-name> ~/.codex/skills/<skill-name>
```

Restart Codex after copying.

## Quick Start

Add the core router set first:

```bash
for s in geepers team swarm quality dream; do
  cp -a "skills/$s" "$HOME/.codex/skills/$s"
done
```

Then add your preferred workflow aliases:

```bash
for s in planner builder testing validator readme humanize; do
  cp -a "skills/$s" "$HOME/.codex/skills/$s"
done
```

## Typical Usage

- `/team`: broad toolbox routing for mixed tasks
- `/swarm`: parallel, broad-spectrum execution
- `/quality`: second-opinion quality audit
- `/dream`: dual-model critique flow (Claude CLI + Gemini CLI in read-only mode)

## Maintenance

When skills change locally in `~/.codex/skills`, sync back into this repo and commit.

## Security

Do not commit secrets, local tokens, or machine-specific config.

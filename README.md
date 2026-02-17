# geepers-gpt

A portable skill pack for GPT-focused CLI workflows.

## What You Get

- Routing helpers: `geepers`, `team`, `swarm`, `quality`, `dream`
- High-utility aliases: `publish`, `doublecheck`, `poet`, `readme`, `humanize`
- Execution flow aliases: `scout`, `planner`, `builder`, `testing`, `validator`
- Source variants kept for compatibility: `dataset-publish`, `geepers-doublecheck`, `geepers-poet`, `geepers-readme`

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

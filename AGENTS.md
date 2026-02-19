# Repository Guidelines

## Project Structure & Module Organization
This repo is a portable skill pack for GPT/Codex workflows.
- `skills/<skill-name>/SKILL.md`: required instructions for each skill.
- `skills/<skill-name>/scripts/`: optional helper scripts (Python utilities, deployment helpers, research tools).
- `README.md`: install and usage patterns for local skill deployment.

Use kebab-case for skill directories (example: `data-fetch`, `git-hygiene-guardian`). Keep each skill self-contained.

## Build, Test, and Development Commands
There is no monolithic build pipeline; validate skills and scripts directly.

```bash
# List all skill definitions
find skills -mindepth 2 -maxdepth 2 -name SKILL.md | sort

# Quick frontmatter check for required keys
rg -n "^(name|description):" skills/*/SKILL.md

# Syntax-check Python helpers
python3 -m compileall skills

# Install a skill locally for manual smoke testing
cp -a skills/<skill-name> ~/.codex/skills/<skill-name>
```

## Coding Style & Naming Conventions
- Start each `SKILL.md` with YAML frontmatter.
- Frontmatter must include `name` and `description`.
- Keep names lowercase kebab-case and aligned with directory names.
- Prefer short, task-oriented Markdown sections with concrete examples.
- Python scripts should follow PEP 8 and avoid hard-coded machine-specific paths.

## Testing Guidelines
- For every changed skill: verify frontmatter keys and run a manual trigger phrase.
- For script changes: run at least one smoke command and a compile check.
- Validate install path by copying changed skills into `~/.codex/skills` and restarting the client.

## Commit & Pull Request Guidelines
Recent history follows Conventional Commit prefixes (`feat:`, `chore:`, `docs:`). Continue that pattern.
- Keep commits scoped to one skill or one logical repo-wide cleanup.
- PRs should include changed skill list, validation commands run, and any behavior differences.
- Include before/after examples for prompt-routing changes.

## Security & Configuration Tips
- Never commit API keys, `.env` files, or local machine credentials.
- Keep generated artifacts (`__pycache__`, `dist`, build outputs) out of commits.

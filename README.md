# geepers-gpt

Generated Codex/GPT skill mirror for the geepers ecosystem.

## Source of Truth

This repository is synced from canonical skills in:
- `https://github.com/lukeslp/geepers`
- Canonical path: `skills/source/`

Direct edits to `skills/` in this repo are blocked by CI. Make changes in canonical source, then sync.

## What Is Here

- `skills/`: generated skill folders for Codex/GPT workflows
- `codex-package.json`: generated package metadata
- `aliases.generated.json`: migration alias map (including Dreamer -> Geepers naming)
- `.github/workflows/mirror-readonly-guard.yml`: mirror protection

## Install

```bash
for s in skills/*; do
  name=$(basename "$s")
  cp -a "$s" "$HOME/.codex/skills/$name"
done
```

Restart your CLI after copying skills.

## Sync Workflow

From canonical repo (`/home/coolhand/geepers`):

```bash
python3 scripts/validate-skills.py --strict
python3 scripts/build-platform-packages.py --platform codex --clean
bash scripts/sync-mirrors.sh --platform codex --delete --skip-build
bash scripts/report-drift.sh --platform codex --skip-missing
```

## License

MIT

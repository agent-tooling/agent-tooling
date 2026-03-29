---
name: agent-tooling
description: Workflow for managing a local mirror of the `agent-tooling` GitHub org and syncing root `AGENTS.md` plus `.agents/` with the `agent-tooling/agent-tooling` repository. Use this whenever the user asks to "update to latest", "save local changes", "fetch latest", or otherwise sync org/repo state.
---

# Agent Tooling Org Workflow

Keep this local structure:

- `agent-tooling/` is the org folder.
- `agent-tooling/agent-tooling/` is the cloned GitHub repository.
- Root metadata lives at `agent-tooling/AGENTS.md` and `agent-tooling/.agents/`.

## Initial setup

1. Create `agent-tooling/` if missing.
2. Clone `git@github.com:agent-tooling/agent-tooling.git` into `agent-tooling/agent-tooling/`.
3. Copy repo-root `AGENTS.md` and `.agents/` into `agent-tooling/`.

## Command mappings

### "update to latest"

Use this when the user wants the local mirror refreshed from GitHub.

1. In `agent-tooling/agent-tooling/`, checkout `main` and pull latest.
2. Copy `AGENTS.md` and `.agents/` from `agent-tooling/agent-tooling/` into `agent-tooling/`.

### "save local changes"

Use this when the user wants local root conventions saved back to GitHub.

1. Copy root workspace `AGENTS.md` and `.agents/` into `agent-tooling/agent-tooling/`.
2. In `agent-tooling/agent-tooling/`, commit and push to `main`.

### "fetch latest"

Use this when the user wants all org repositories synced.

1. Use `gh` to list all repositories under `agent-tooling`.
2. For each repository:
   - If missing locally, clone via SSH into `agent-tooling/<repo-name>/`.
   - If already present, checkout `main` and pull latest.

## Notes

- Prefer SSH remotes (`git@github.com:...`) for all clones.
- Do not overwrite unrelated local changes without user confirmation.

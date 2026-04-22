# Agent Tooling

Agent Tooling (github.com/agent-tooling) is a GitHub organization revolving around AI and developer tools.

## Local Mirror Layout

The workspace root is the **org mirror folder**. Each cloned org repo is a direct child of it. The meta-repo (`agent-tooling/agent-tooling`) lives at the nested path `./agent-tooling/` and holds the source-of-truth `AGENTS.md` + `.agents/` that are mirrored to the root.

```
./                        <- org mirror folder (this workspace root)
├── AGENTS.md             <- working copy (this file), synced with the meta-repo
├── .agents/              <- working copy, synced with the meta-repo
├── agent-tooling/        <- clone of github.com/agent-tooling/agent-tooling (meta-repo)
├── message-layer/        <- clone of github.com/agent-tooling/message-layer
└── <other-repo>/         <- other org repos as siblings
```

Critical: sibling org repos go at `./<repo-name>/` — **never** inside `./agent-tooling/<repo-name>/`. See the `agent-tooling` skill for the full sync workflow ("update to latest", "save local changes", "pull <repo>", "fetch latest").

## Dev Workflow

For every task, do the following:

- Make sure you're on the `main` branch (or the appropriate feature branch)
- Make sure you pull the latest changes
- Make the changes
- Review the CONTRIBUTING.md file for the project you're working on and run formatting, linting, and testing as appropriate
- Commit the changes
- Push the changes to the remote repository

Important: If the changes aren't trivial or required several conversations back and forth, make sure to hold off on committing until the changes were reviewed and approved. Use your best judgement to determine if the changes are trivial or not.

## Best Practices

- all files names in kebab-case
- every repo in the org ships a `.gitignore` that excludes `.env` / `.env.*`
  (other than `.env.example`) so secrets never land in version control.
  The meta-repo's top-level `.gitignore` is the canonical template; sibling
  repos may extend it with project-specific rules but must not weaken the
  secret exclusion.

## Way of Working

### What to document

Important: If we're iterating quickly on a task/feature and revert back or refactor, you must not document the deleted code or changes in comments. Comments like: "Removed this code because XYZ" is not valuable context. Only document and comment the final working code and emphasize the final solution in commit messages, PR descriptions, and documentation. Documenting what we didn't do is not valuable context.

## Tooling

- GitHub: Use the GitHub CLI (`gh`) for all GitHub-related tasks like creating PRs, reviewing PRs, etc.
- git: Use `git` for all git-related tasks like committing, pushing, pulling, etc.
- `npm`: Use `npm` for publishing packages to npm and bumping package versions.
- `pnpm`: Use `pnpm` as the package manager for all TypeScript projects.
- `node`: Use `node` (>=22) as the runtime for all TypeScript/JavaScript projects. Use `tsx` to run TypeScript directly in development.
- `vitest`: Use `vitest` for testing.
- `agent-browser`: `agent-browser` is installed globally and must be used for browser interactions. Store screenshots in `./screenshots/<project-name>/`
- Use termshot to generate terminal screenshots

## References & Demos

Neither of these folders are to be released on GitHub.

- `./.references/` to host reference codebases to learn from.
- `./.demos/` to host demos of the tools we're building and iterate on the DX.
- `./.videos/` to create launch/update remotion videos for the tools we're building.
- `./.screenshots/` for temporary screenshots by `agent-browser`.

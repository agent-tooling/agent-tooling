# Agent Tooling

Agent Tooling (github.com/agent-tooling) is a GitHub organization revolving around AI and developer tools.

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

## Way of Working

### What to document

Important: If we're iterating quickly on a task/feature and revert back or refactor, you must not document the deleted code or changes in comments. Comments like: "Removed this code because XYZ" is not valuable context. Only document and comment the final working code and emphasize the final solution in commit messages, PR descriptions, and documentation. Documenting what we didn't do is not valuable context.

## Tooling

- GitHub: Use the GitHub CLI (`gh`) for all GitHub-related tasks like creating PRs, reviewing PRs, etc.
- git: Use `git` for all git-related tasks like committing, pushing, pulling, etc.
- `npm`: Use `npm` for publishing packages to npm and bumping package versions.
- `bun`: Use `bun` as the package manager (not npm) for all TypeScript projects.
- `vitest`: Use `vitest` for testing - not bun test.
- `agent-browser`: `agent-browser` is installed globally and must be used for browser interactions. Store screenshots in `./screenshots/<project-name>/`
- Use termshot to generate terminal screenshots

## References & Demos

Neither of these folders are to be released on GitHub.

- `./.references/` to host reference codebases to learn from.
- `./.demos/` to host demos of the tools we're building and iterate on the DX.
- `./.videos/` to create launch/update remotion videos for the tools we're building.
- `./.screenshots/` for temporary screenshots by `agent-browser`.

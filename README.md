# design-agent-rules

A set of workspace design rules for AI coding agents such as Codex and Claude Code, covering UI design, frontend implementation, brand design, posters, presentations, and product images, with corresponding review criteria.

## Installation

Copy the repository contents into the root of your workspace, or into the folder where design work happens. Codex reads `AGENTS.md`; Claude Code reads `CLAUDE.md`, which includes `AGENTS.md`. The rules apply to that folder and its subfolders.

## Usage

The agent enters from [AGENTS.md](AGENTS.md) and reads selectively via task routing. Existing projects keep their own codebase and current records; for new projects, the user's request determines the deliverables. The documents do not include tools, account capabilities, or publishing authorization.

- [Design Library Navigation](library/README.md): entry to methods, specialized references, and optional parameters.
- [Project Record Templates](templates/project/index.md): choose by task size; filling in everything is not required.

## Contents

| Folder | Purpose |
|---|---|
| `standards/` | Shared rules: scope, workflow, defaults, components, quality |
| `domains/` | Workflow, method, and acceptance for UI, frontend, brand, poster, presentation, and commerce |
| `library/` | Optional presets, style references, and review references |
| `templates/` | Project record templates |
| `knowledge/` | How reusable lessons are promoted into rules |

## License

[MIT](LICENSE)

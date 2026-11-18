# design-agent-rules

A set of workspace design rules for AI coding agents such as Codex and Claude Code, covering UI design, frontend implementation, brand design, posters, presentations, and product images, with corresponding review criteria.

## Installation

For a new workspace, extract the archive and open the folder containing `AGENTS.md` as your workspace root.

For an existing project, copy that folder to an unused path such as `design/`, keeping the project's agent instructions, README, and license in place. The rules apply within that folder and its subfolders. To use them for design work across the project, add a line to the root instructions your agent reads, using the actual installation path. For example, “For design tasks and related frontend implementation or review, follow the applicable sections of `design/AGENTS.md`.”

## Usage

The agent enters from [AGENTS.md](AGENTS.md) and reads selectively via task routing. Existing projects keep their own codebase and current records; for new projects, the user's request determines the deliverables.

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

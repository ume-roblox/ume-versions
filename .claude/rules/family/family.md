# The ume family

*Shared rule: an identical copy sits in `.claude/rules/family/` of every ume repo. Change all copies together (Shared files, below).*

The family is nine sibling repos, checked out next to each other in one parent folder, so each reaches the others as `../<repo>`:

| Repo | What it is | Stack |
| --- | --- | --- |
| `ume` | The Roblox game framework every game starts from: modules, libraries, components, checked remotes, saved data, all reached through `I` | Luau |
| `ume-gui` | UmeGui, guis written as tables, and the engine every game's `<game>-gui` folder is copied from | Luau |
| `new-project` | The template every new game repo is made from: its setup copies ume and ume-gui into the game's two folders | PowerShell, Markdown |
| `ume-rbx` | The Ume Roblox Studio plugin (Sync, Gui, TagList+ and other tools). Builds its widgets on a copy of ume-gui | Luau |
| `ume-sync` | UmeSync, the tray app and local hub that syncs project folders into Studio, one way, with an MCP server for agents | Rust, Tauri, Svelte |
| `ume-lsp` | The Luau language server, shipped as a VS Code extension and also run headless by ume-sync | TypeScript, Lua |
| `ume-vscode` | The VS Code extension: themes, snippets, the Create and Extract commands, the author stamp | TypeScript |
| `ume-versions` | The family's public front page and the version badges | Markdown, JSON, SVG |
| `.github-private` | The organisation's members-only profile page | Markdown, SVG |

A game is one more repo, made from `new-project`: `<game>-game` (a copy of ume) and `<game>-gui` (a copy of ume-gui), two UmeSync projects in one category, both syncing into `<game>.rbxl`.

## Boundaries

- Work in the repo you were asked about. Read siblings freely; change one only when the user asks, and say which files you touched there.
- When a change needs a matching change in a sibling (a protocol, the headless interface, a vendored copy, a shared file), name it and ask, unless the user already asked for both.
- Each repo's `AGENTS.md` lists what it relies on from its siblings, under **Working across repos**.

## Agent files

Every repo has the same layout:

| Path | What |
| --- | --- |
| `AGENTS.md` | The guide for any agent: what the repo is, read first, commands, repo map, skills, working across repos |
| `CLAUDE.md` | `@AGENTS.md`, then notes for Claude Code only |
| `.claude/rules/**/*.md` | Rules. A file without `paths:` frontmatter always loads; a file with `paths:` loads when a matching file is read or edited. |
| `.claude/skills/<name>/SKILL.md` | Step-by-step playbooks, run as `/<name>`. Any agent can read them. |

Rules are the only full statement of a constraint. Each fact has one owner rule; other rules, docs and skills link to it instead of restating it. Don't copy rule text into `AGENTS.md`, `CLAUDE.md` or `docs/`.

## Shared files

Some files are identical copies in several repos:

| Files | Repos |
| --- | --- |
| `.claude/rules/family/*` | every repo except new-project |
| `.claude/rules/luau/*`, `.claude/skills/readme/*` | ume, ume-rbx, ume-gui |

new-project has no family rules of its own: a game made from it carries them inside its two folders.

Change one copy, then make the same change to every other copy in the same piece of work. Copies may differ only in line endings (ume-lsp uses CRLF). To list the files whose copies differ, from the parent folder in PowerShell:

```powershell
Get-ChildItem */.claude/rules/family/*, */.claude/rules/luau/*, */.claude/skills/readme/* -File | Group-Object Name | Where-Object { ($_.Group | ForEach-Object { (Get-Content -Raw $_.FullName) -replace "`r" } | Select-Object -Unique).Count -gt 1 } | ForEach-Object Name
```

## Temporary files

Clones, scripts, test projects, builds and screenshots go in the session's scratchpad (or the system temp folder), never in a repo.

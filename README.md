<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/assets/banner-dark.svg">
  <img alt="Ume: tools for building Roblox games, from your editor to Studio. A framework, a language server, a VS Code extension, a sync app and a Studio plugin." src="docs/assets/banner-light.svg" width="100%">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/assets/intro-dark.svg">
  <img alt="Ume is a family of tools for making Roblox games: a Luau framework to build on, a language server and a VS Code extension to write it with, a tray app that syncs your project into Studio, and a Studio plugin to finish the work there. Pick the pieces you need; together they make one path from editor to place." src="docs/assets/intro-light.svg" width="100%">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/assets/family-dark.svg">
  <img alt="The family in four stages: the Ume framework, then Ume LSP and Ume VSCode in your editor, then UmeSync, then the Ume Roblox plugin in Studio." src="docs/assets/family-light.svg" width="100%">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/assets/panel-workflow-dark.svg">
  <img alt="From your editor to Studio: a ume module in VS Code with Ume LSP completing the framework's Network API, UmeSync syncing the project, and the module selected in Studio's Explorer." src="docs/assets/panel-workflow-light.svg" width="100%">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/assets/panel-agents-dark.svg">
  <img alt="Ready for agents: the framework ships rules and job plans for Claude Code and Cursor, and UmeSync's MCP server shows them your projects, their instances and selene, StyLua and ume-lsp checks." src="docs/assets/panel-agents-light.svg" width="100%">
</picture>

## The family

| | Repository | |
| --- | --- | --- |
| **Ume** | [ume](https://github.com/ume-roblox/ume) | A lightweight Luau framework for Roblox games: modules, tagged components, checked remotes and saved player data |
| **Ume Gui** | [ume-gui](https://github.com/ume-roblox/ume-gui) | UmeGui, guis as tables: a theme for every look, previews and exports in Studio, at every device size |
| **New Project** | [new-project](https://github.com/ume-roblox/new-project) | The template for a new game: one repo whose setup copies Ume and Ume Gui into `<game>-game` and `<game>-gui` |
| **Ume LSP** | [ume-lsp](https://github.com/ume-roblox/ume-lsp) | A Luau language server for VS Code: completion, types and diagnostics that know the Roblox API and your project's instance tree |
| **Ume VSCode** | [ume-vscode](https://github.com/ume-roblox/ume-vscode) | The Ume and Ume Light themes, Luau snippets, and commands that write modules, components and data files from templates |
| **UmeSync** | [ume-sync](https://github.com/ume-roblox/ume-sync) | A tray app that syncs project folders into Studio: Rojo-compatible, many projects into many Studios, with MCP for agents |
| **Ume Roblox** | [ume-rbx](https://github.com/ume-roblox/ume-rbx) | One Studio plugin: live sync with a review of every change, UmeGui, scene tools and a Team Create session lock |

## How it fits together

1. **Build on Ume.** Every module, component and data file has its place, and they all start in one order on the server
   and the client. A game starts from New Project, which puts the game's code and its guis (a copy of Ume Gui) side
   by side in one repo.
2. **Write in VS Code.** Ume LSP completes and checks your Luau as you type. Ume VSCode makes new modules, components
   and data files in the framework's layout.
3. **Sync with UmeSync.** Add the project folder once; it serves every project from one local hub.
4. **Finish in Studio.** Ume Roblox's Sync tool connects to the hub, shows what will change and keeps the place in step.
   Its other tools take care of guis, lighting, tags, pictures and avatars.

Most pieces work on their own too: the framework with any Rojo-compatible sync, Ume LSP in any Luau workspace, the plugin's gui and scene
tools without the app.

## Version badges

`src/` holds a [shields.io endpoint](https://shields.io/badges/endpoint-badge) file per repository with its current
version, for other READMEs to show:

```md
![Ume](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/ume-roblox/ume-versions/refs/heads/main/src/framework.json)
```

`framework.json`, `gui.json`, `lsp.json`, `vscode-extension.json`, `roblox-extension.json` and `sync.json`.

---

<div align="center">

**Ume is released under a custom [licence](LICENSE.md)**
<br>
Maintained with 😭 by <b>Nari</b>

</div>

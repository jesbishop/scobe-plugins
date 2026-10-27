# Scobe

Scobe is an infinite canvas of live browsers and editable frames. With this plugin your agent can build on the canvas while you watch: create frames with auto-layout, add text and shapes, style them, and snapshot any live web page into editable layers.

## Prerequisites

Install [Scobe](https://github.com/jesbishop/scobe/releases/latest) for Windows, macOS, or Linux and open it at least once. Keep the app open while your agent works.

## Features

- **Read the canvas**: List frames, layers, and live browsers, with their sizes and hierarchy.
- **Write to the canvas**: Create artboards and auto-layout frames, add text, rectangles, and ellipses, then move, resize, restyle, rename, duplicate, or delete them.
- **Snapshot live pages**: Pull any region of an open browser into the canvas as editable layers, not a flat screenshot.
- **Drive browsers**: Open and navigate live browsers on the canvas and take screenshots of them.

## Examples

**Prompt:** "Build a landing page hero on the Scobe canvas with auto-layout."

Your agent checks the canvas, creates a frame with auto-layout, and adds a headline, subtext, and buttons. New layers shimmer on the canvas as they appear.

**Prompt:** "Snapshot the sidebar from my open browser into editable layers in Scobe."

Your agent finds the open browser, snapshots the sidebar, and places it beside the browser as layers you can restyle.

## Install

### Claude Code

```sh
/plugin install scobe --marketplace jesbishop/scobe-plugins
```

On Claude Code versions before 2.1.275, add the marketplace first with `/plugin marketplace add jesbishop/scobe-plugins`, then run `/plugin install scobe@scobe`.

### Cursor

```sh
/add-plugin scobe
```

### Codex

```sh
codex mcp add scobe --url http://127.0.0.1:29980/mcp
```

## What this plugin runs and connects to

- The plugin starts one local MCP server: the bridge script in this plugin, [`server/scobe-mcp.cjs`](server/scobe-mcp.cjs), a short, dependency-free Node script you can read in full.
- Claude Code runs it with the `scobe` command at `~/.scobe/bin/scobe`, which the Scobe desktop app installs each time it starts. That command is Scobe's own bundled runtime in Node mode, so nothing is downloaded or installed when the plugin starts.
- The bridge talks only to the Scobe app on your computer at `http://127.0.0.1:29980/mcp`. It makes no other network requests and sends no data anywhere else.
- When Scobe is closed, the bridge reads the tool list Scobe saved at `~/.scobe/mcp-cache.json` and answers tool calls with "Scobe is not open".

## License

MIT

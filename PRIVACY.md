# Scobe plugin privacy policy

Effective October 26, 2026

This policy covers the Scobe plugin for Claude Code, Cowork, Cursor, and Codex (this repository). The plugin connects your coding agent to the Scobe desktop app on your own computer.

## What the plugin reads

When your agent calls one of Scobe's tools, the plugin reads what that tool asks for from the Scobe app: the frames, layers, and text on your canvas, and, for browser tools, screenshots or snapshots of pages open in Scobe. Those pages can contain personal information, such as names or email addresses, if you have them open. The plugin passes the result to your agent, and your agent's provider handles it under its own privacy policy (for Claude, Anthropic's).

## What the plugin stores

Nothing about you. The only file it reads from disk is `~/.scobe/mcp-cache.json`, the list of Scobe's tools that the app saves so your agent can see them while Scobe is closed.

## What the plugin sends, and where

The plugin talks only to the Scobe app on your computer, at `http://127.0.0.1:29980/mcp`. It makes no other network requests. It has no analytics, telemetry, or tracking, and the developer receives no data from it.

## Changes

If this changes, this file will be updated and the change will be visible in this repository's history.

## Contact

Open an issue at [github.com/jesbishop/scobe-plugins/issues](https://github.com/jesbishop/scobe-plugins/issues).

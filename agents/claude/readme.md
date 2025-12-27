---
id: claude
name: Claude Desktop
description: Anthropic's AI assistant desktop app
category: chat
icon: icon.png
color: "#D97757"

platforms:
  macos:
    app_path: /Applications/Claude.app
    config_path: ~/Library/Application Support/Claude/claude_desktop_config.json
  windows:
    app_path: "%LOCALAPPDATA%/Programs/Claude/Claude.exe"
    config_path: "%APPDATA%/Claude/claude_desktop_config.json"
---

# Claude Desktop

Anthropic's AI assistant desktop app with native MCP support.

## Setup

1. Click **Install to Claude Desktop** in agentOS
2. Restart Claude Desktop to load the MCP configuration
3. Your apps will be available automatically

## Instructions for AI

You are running in the Claude Desktop app.

- MCP config: ~/Library/Application Support/Claude/claude_desktop_config.json
- Restart Claude Desktop to reload MCP config changes

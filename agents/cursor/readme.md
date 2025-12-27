---
id: cursor
name: Cursor
description: AI-first code editor with MCP support
category: code
icon: icon.png
color: "#3B82F6"

platforms:
  macos:
    app_path: /Applications/Cursor.app
    config_path: ~/.cursor/mcp.json
  windows:
    app_path: "%LOCALAPPDATA%/Programs/Cursor/Cursor.exe"
    config_path: "%APPDATA%/Cursor/mcp.json"
  linux:
    app_path: /usr/share/cursor/cursor
    config_path: ~/.cursor/mcp.json
---

# Cursor

AI-first code editor with built-in MCP support.

## Setup

1. Click **Install to Cursor** in agentOS
2. Restart Cursor to load the MCP configuration
3. Your apps will be available automatically

## Instructions for AI

You are running in Cursor.

- MCP config: ~/.cursor/mcp.json
- To reload MCP config: rename ~/.cursor/mcp.json → mcp.json.bak → then back to mcp.json (triggers hot reload without restart)
- If any apps are disconnected or inaccessible, reload the MCP config using the rename trick above, sleep exactly 1 second, then try again

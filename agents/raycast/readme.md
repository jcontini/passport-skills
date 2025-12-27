---
id: raycast
name: Raycast
description: Mac productivity tool with AI chat
category: chat
icon: icon.png
color: "#FF6363"

platforms:
  macos:
    app_path: /Applications/Raycast.app

install:
  method: deeplink
  deeplink_url: "raycast://mcp/install?{{config_json}}"
---

# Raycast

Mac productivity tool with AI chat features and MCP support.

## Setup

1. Click **Install to Raycast** in agentOS
2. Press ⌘+Enter in the Raycast dialog to confirm
3. Type `@agentOS` in any AI chat to use your apps

**Optional:** [Add to a preset for automatic loading →](https://manual.raycast.com/ai#ai-chat-presets)

## Instructions for AI

You are running in Raycast AI.

- Type @agentOS in any AI chat to use apps
- MCP is configured via Raycast → Settings → Extensions → AI → MCP Servers

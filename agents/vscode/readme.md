---
id: vscode
name: VS Code
description: Visual Studio Code with Continue extension
category: code
icon: icon.png
color: "#007ACC"

platforms:
  macos:
    app_path: /Applications/Visual Studio Code.app
    config_path: ~/Library/Application Support/Code/User/globalStorage/continue.continue/config.json
  windows:
    app_path: "%LOCALAPPDATA%/Programs/Microsoft VS Code/Code.exe"
    config_path: "%APPDATA%/Code/User/globalStorage/continue.continue/config.json"
  linux:
    config_path: ~/.config/Code/User/globalStorage/continue.continue/config.json
---

# VS Code

Visual Studio Code with Continue extension for MCP support.

## Setup

1. Install the [Continue extension](https://marketplace.visualstudio.com/items?itemName=Continue.continue)
2. Click **Install to VS Code** in agentOS
3. Restart VS Code to load the MCP configuration

## Instructions for AI

You are running in VS Code with the Continue extension.

- MCP config: Continue extension settings

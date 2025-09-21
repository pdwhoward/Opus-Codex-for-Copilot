# Opus & Codex for Copilot - VS Code Extension

Integrate Claude Code and GPT Codex subscriptions into GitHub Copilot through local proxy servers.

## Model Configurations

### Claude Models (Port 8081)

| Model | Input Tokens | Output Tokens |
|-------|-------------|---------------|
| **Claude Opus 4.1** | 200,000 | 32,000 |
| **Claude Sonnet 4** | 200,000 | 64,000 |

### Codex Models (Port 8000)

| Model | Input Tokens | Output Tokens |
|-------|-------------|---------------|
| **GPT-5** | 272,000 | 128,000 |
| **GPT-5 High** | 272,000 | 128,000 |
| **GPT-5 Codex** | 272,000 | 128,000 |
| **GPT-5 Codex High** | 272,000 | 128,000 |
| **Codex Mini** | 200,000 | 100,000 |

## Prerequisites

- **VS Code Insiders** (required for Language Model Chat Provider API)
  - Download from: https://code.visualstudio.com/insiders/
- **Python 3.7+** with pip
- **Git** for cloning proxy repositories
- **Accounts**:
  - Claude Pro/Max account (for Claude models)
  - ChatGPT Plus/Pro account (for GPT/Codex models)

## Installation

### Step 1: Install the Extension

Install the extension VSIX file in VS Code Insiders:

```bash
code-insiders --install-extension vscode-claude-codex-1.0.0.vsix --force
```

After installation, reload VS Code Insiders (`Ctrl+Shift+P` → "Developer: Reload Window")

### Step 2: Install and Configure Proxy Servers

The extension requires proxy servers running locally. You can run one or both depending on which models you want to use.

#### Option A: Claude Models (Opus 4.1, Sonnet 4)

Clone and set up the anthropic-claude-max-proxy repository:
```bash
git clone https://github.com/Pimzino/anthropic-claude-max-proxy.git
```
Follow the setup instructions in the repository to authenticate and run the proxy on port 8081.

#### Option B: GPT/Codex Models (GPT-5, Codex Mini)

Clone and set up the ChatMock repository:
```bash
git clone https://github.com/RayBytes/ChatMock.git
```
Follow the setup instructions in the repository to authenticate and run the proxy on port 8000.

## Verify Installation

1. Open VS Code Insiders
2. Open the Chat panel (`Ctrl+Shift+I` or `Cmd+Shift+I` on Mac)
3. Click the model dropdown in the chat panel
4. You should see the following models under "Opus & Codex for Copilot":
   - **Claude Models** (if anthropic proxy is running):
     - Opus 4.1
     - Sonnet 4
   - **GPT/Codex Models** (if ChatMock is running):
     - GPT-5
     - GPT-5 High
     - GPT-5 Codex
     - GPT-5 Codex High
     - Codex Mini

## Usage

### Port conflicts
- If ports 8081 or 8000 are already in use, either:
  - Stop the conflicting service, or
  - Use different ports when starting the proxies and update VS Code settings accordingly

### Extension not appearing in model list
- Ensure you're using VS Code **Insiders** (not regular VS Code)
- Reload the window after installation
- Check Output panel (`View` → `Output` → Select "Opus & Codex Proxies") for errors

## Notes

- Both proxy servers must remain running while using their respective models
- Proxy servers authenticate using OAuth (not API keys) with your existing Claude/ChatGPT accounts
- The extension works with the original, unmodified proxy repositories
- You can run just one proxy if you only need either Claude or GPT models

## Disclaimer

**THIS SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.**

**This extension is not affiliated with, endorsed by, or sponsored by Microsoft, GitHub, Anthropic, or OpenAI. This is an independent project created solely for educational purposes.**

**Use of this extension requires compliance with the terms of service of all involved parties including but not limited to VS Code, GitHub Copilot, Claude, and OpenAI.**

## License

MIT License

Copyright (c) 2025

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
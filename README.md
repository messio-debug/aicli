# aicli
Lightweight terminal AI CLI hub with provider failover.

`aicli` gives you one terminal chat interface and routes prompts to installed AI CLIs (Gemini, Codex, OpenCode, Aider, LLM, GitHub Copilot CLI). If one provider hits quota/rate limits, it can switch to another.

## Features

- Interactive REPL chat + one-shot prompt mode
- Provider login/activation flow (`/accounts`)
- Auto-failover on quota/rate-limit indicators
- Account/provider switching (`/switch`)
- Permission modes (`/permission project|full`)
- Auto-accept toggle (`/autoaccept on|off`)
- Background command runner (`/bg <cmd>`)
- Works on Linux (Arch/Gentoo friendly)

## Install (Arch/Gentoo, no pip required)

```bash
git clone <your-repo-url> ~/aicli
cd ~/aicli
chmod +x install-arch.sh
./install-arch.sh
If ~/.local/bin is not in PATH:
export PATH="$HOME/.local/bin:$PATH"

Run
aicli
aicli -p "explain this repo"
aicli --accounts

Commands
- /accounts - list/login providers
- /switch <id|number> - change active provider
- /permission <project|full> - set permission mode
- /autoaccept <on|off> - toggle auto-accept
- /bg <shell command> - run command in background with log file
- /status - show current config
- /help, /quit
Config
Config file: ~/.config/aicli/config.json  
Background logs: ~/.local/state/aicli/

Notes
This does not bypass provider auth or quotas. It orchestrates installed provider CLIs and fails over when limits are detected.

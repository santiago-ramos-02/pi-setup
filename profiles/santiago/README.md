# Santiago's Pi agent profile

This is Santiago's personal user-wide Pi agent configuration. It is not a general baseline and is not needed to use any module or skill. It contains model/provider defaults, global instructions, agent definitions, subagent mappings, and a review chain.

The `agent/` directory mirrors `~/.pi/agent`. Inspect each file and selectively copy only what you want. Avoid overwriting a machine's existing configuration wholesale. On Windows the destination is `%USERPROFILE%\.pi\agent`; on Linux it is `~/.pi/agent`.

## Files

- `agent/settings.json`: defaults and TUI settings.
- `agent/models.json`: model definitions for the selected provider setup.
- `agent/AGENTS.md` and `agent/APPEND_SYSTEM.md`: global instructions. `APPEND_SYSTEM.md` includes Engram observation-only guidance; neutral-language or persona preferences are not set here.
- `agent/subagents.json`, `agent/agents/`, and `agent/chains/`: orchestration mappings, agent prompts, and review chain.

The main model is configured as `openai-codex/gpt-6-astra`. Some delegated roles use Muse through OpenCode Go, which requires that provider to be separately available and authenticated on the target machine. No credentials are included. If a provider or model is unavailable, adapt the relevant model IDs rather than copying auth files.

This profile was prepared for Santiago's current Windows workflow. It contains no WSL-only runtime instructions. Keep provider sign-in, sessions, and local caches on each machine.

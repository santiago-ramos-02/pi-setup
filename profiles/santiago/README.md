# Santiago's Pi agent profile

These are Santiago's personal Pi/Gentle-Pi configurations. They are not a general baseline and are not needed to use any module or skill. Each named profile is a readable file set, not a profile-switching tool.

The `gentle-ai-low-cost/`, `gentle-ai-recommended/`, and `gentle-ai-powerful/` folders are Gentle-AI profiles adapted for Pi/Gentle-Pi. They keep Gentle-AI's tier names and agent-lane assignments, updated here to GPT-6 with Terra replaced by Sol. Inside each, `codex/` and `opencode/` select the model provider used by Pi. These files do not configure the standalone Codex or OpenCode apps.

The `agent/` directory is the full Astra baseline and mirrors `~/.pi/agent`. The `opencode-free/` and `opencode-go/` folders contain Muse model variants for Pi. In each profile, `settings.json` selects the main model and `subagents.json` sets Gentle-Pi's delegated model assignments. Apply or merge the chosen files manually; do not overwrite the rest of `~/.pi/agent`. On Windows the destination is `%USERPROFILE%\.pi\agent`; on Linux it is `~/.pi/agent`.

## Available profiles

- [`agent/`](agent/): Santiago's Astra high-reasoning setup snapshot, including prompts, agents, and chains.
- [`gentle-ai-low-cost/`](gentle-ai-low-cost/README.md): Gentle-AI Low-cost profile adapted for Pi, with Codex and OpenCode provider variants.
- [`gentle-ai-recommended/`](gentle-ai-recommended/README.md): Gentle-AI Recommended profile adapted for Pi, with Codex and OpenCode provider variants.
- [`gentle-ai-powerful/`](gentle-ai-powerful/README.md): Gentle-AI Powerful profile adapted for Pi, with Codex and OpenCode provider variants.
- [`opencode-free/`](opencode-free/README.md): Muse Spark 1.3 Contributor Free as the main Pi model and for delegated work.
- [`opencode-go/`](opencode-go/README.md): Muse Spark 1.3 Contributor through OpenCode Go as the main Pi model and for delegated work.

## Files

- `agent/settings.json`: defaults and TUI settings.
- `agent/models.json`: model definitions for the selected provider setup.
- `agent/AGENTS.md` and `agent/APPEND_SYSTEM.md`: global instructions. `APPEND_SYSTEM.md` includes Engram observation-only guidance; neutral-language or persona preferences are not set here.
- `agent/subagents.json`, `agent/agents/`, and `agent/chains/`: orchestration mappings, agent prompts, and review chain.

The main model in the baseline is `openai-codex/gpt-6-astra`. Some delegated roles use Muse through OpenCode Go, which requires that provider to be separately available and authenticated on the target machine. No credentials are included. If a provider or model is unavailable, adapt the relevant model IDs rather than copying auth files.

These are adaptations of Gentle-AI's published Codex Low-cost, Recommended, and Powerful profiles. They use GPT-6 and map Terra to Sol as requested. In this repository they configure Pi/Gentle-Pi, with `openai-codex` or `opencode` as the model provider. See [Gentle-AI's agent guidance](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/agents.md#codex) and [Pi integration notes](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/pi.md).

This profile was prepared for Santiago's current Windows workflow. It contains no WSL-only runtime instructions. Keep provider sign-in, sessions, and local caches on each machine.

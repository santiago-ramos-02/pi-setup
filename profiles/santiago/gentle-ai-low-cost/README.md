# Gentle-AI Low-cost

GPT-6 adaptation of Gentle-AI's Low-cost preset, for the Codex and OpenCode model providers in Pi/Gentle-Pi. The main session and strong/mid lanes use GPT-6 Sol at medium effort; the cheap lane uses GPT-6 Luna at high effort. Terra is replaced by Sol, as requested.

This is a manual Pi profile snapshot, not a native Codex CLI or OpenCode configuration. Choose either `codex/` or `opencode/` and merge its `settings.json` and `subagents.json` into `%USERPROFILE%\.pi\agent` (Windows) or `~/.pi/agent` (Linux), preserving unrelated settings and packages. Restart Pi or start a new session after applying.

The default lane covers init, onboarding, research, specs, task breakdown, status, archive, and readability review with Luna/high. Strong roles use Sol/medium; apply, remediation, fix, and worker roles use Sol/medium. See [Gentle-AI's published Codex lanes](https://github.com/Gentleman-Programming/gentle-ai/blob/main/docs/agents.md#codex).

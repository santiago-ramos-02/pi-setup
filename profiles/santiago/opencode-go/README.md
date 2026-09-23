# OpenCode Go model profile

This Pi profile uses Muse Spark 1.3 Contributor through OpenCode Go for both the main session and Gentle-Pi delegated agents.

- Main model: `opencode-go/muse-spark-1.3-contributor`
- Delegated models: same model for all roles
- Main reasoning: medium
- Delegated reasoning: low for init/status/archive; medium for onboarding/readability; high for SDD exploration/research/proposal/spec/task work plus Gentle-AI exploration/worker; xhigh for design, implementation, verification, remediation, judges, and risk/resilience/reliability reviews
- Provider access: OpenCode Go must be available and authenticated on the machine

The exact model ID was present in Santiago's `opencode models` catalog when this profile was recorded. Catalog availability can change. Confirm it with `opencode models` before applying the profile. This folder contains no credentials.

## Apply

Merge `agent/settings.json` into `%USERPROFILE%\.pi\agent\settings.json` (Windows) or `~/.pi/agent/settings.json` (Linux), changing only `defaultProvider`, `defaultModel`, and `defaultThinkingLevel`. Then merge `agent/subagents.json` into the same folder as `subagents.json`. Preserve unrelated settings, providers, packages, and local files. Restart Pi and check the selected model before starting work.

This is a manual configuration snapshot, not a built-in Pi profile switcher. To return to the Astra setup, restore its `settings.json` and `subagents.json` from [`../agent/`](../agent/).

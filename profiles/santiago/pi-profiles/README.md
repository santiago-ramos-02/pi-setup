# Pi model profiles

Each JSON file here is a single-profile export for Gentle-Pi's `/gentle:profiles` selector. The installed profiles on Santiago's Windows Pi match these exports. `opencode-free.json` is an optional definition that is not installed on his machine because Pi currently has no `opencode` provider or Free Muse model in its catalog.

## Choose a profile

| File | Main model | Purpose |
| --- | --- | --- |
| `recommended.json` | Sol, medium | Santiago's custom mix of Sol, Luna, and Muse Go. This is not Gentle-AI's Recommended preset. |
| `gentleman-original.json` | Sol, medium | Santiago's earlier Gentleman routing. |
| `high-reasoning.json` | Astra, high | Santiago's expensive profile for difficult work. |
| `gentle-ai-low-cost.json` | Luna, medium | Gentle-AI Codex Low-cost preset adapted to Pi. |
| `gentle-ai-recommended.json` | Sol, medium | Gentle-AI Codex Recommended preset adapted to Pi. |
| `gentle-ai-powerful.json` | Astra, medium | Gentle-AI Codex Powerful preset adapted to Pi. |
| `opencode-go.json` | Muse Spark 1.3 Contributor, medium | Muse through Pi's `opencode-go` provider. |
| `opencode-free.json` | Muse Spark 1.3 Contributor Free, medium | Optional. Requires a Pi provider exposing `opencode/muse-spark-1.3-contributor-free`. |

The three Gentle-AI profiles use the [Codex preset matrix in Gentle-AI's source](https://github.com/Gentleman-Programming/gentle-ai/blob/c5da5fd0f5f0a0b34cfc9bca0a8b5dd5a46213a8/internal/model/codex_model.go). That source already uses GPT-6. Its older `docs/agents.md` prose still describes GPT-5.6, so these files follow the code. The Codex presets and Pi's profile selector are separate systems; these exports translate the preset routing into Pi's 24 named roles.

| Gentle-AI preset | Main session | Reasoning lane | Coding lane | Lightweight lane |
| --- | --- | --- | --- | --- |
| Low-cost | Luna, medium | Sol, medium | Luna, medium | Luna, high |
| Recommended | Sol, medium | Sol, medium | Luna, high | Luna, high |
| Powerful | Astra, medium | Astra, xhigh | Sol, high | Luna, high |

These tier names compare Gentle-AI's Codex-only presets. Santiago's custom `recommended` profile routes nine roles to Muse Go, so the preset named Low-cost is not necessarily cheaper for his workload.

Gentle-AI puts SDD explore, research, proposal, design, verify, and the two Judgment Day judges in the reasoning lane; SDD apply and `jd-fix-agent` in the coding lane; and SDD onboard, spec, tasks, and archive in the lightweight lane. Pi's `sdd-proposal` is the counterpart to Gentle-AI's `sdd-propose`.

The extra Pi roles follow the same work types: init and status, readability review, and general exploration use the lightweight lane; remediation and general workers use the coding lane; risk, resilience, reliability, validator, and general verification use the reasoning lane. These extensions are local policy, not upstream Codex assignments.

## Import one profile

1. Confirm the profile's provider and model appear in `pi --list-models` and sign in to that provider on this machine.
2. Copy the chosen JSON file to `%USERPROFILE%\.pi\gentle-ai\profiles.export.json` on Windows or `~/.pi/gentle-ai/profiles.export.json` on Linux.
3. Open `/gentle:profiles` in Pi and press `i` to import. Select the new entry and press Enter when you want to apply it.

Importing adds a named profile; applying one changes the main model and all agent routes. The importer refuses an existing name, so inspect or rename an existing profile before importing a replacement. Keep the currently active profile until you choose to switch. The files contain model routing only, with no credentials, sessions, prompts, or Engram observations.

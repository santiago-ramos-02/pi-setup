# Model profiles

These are Gentle-Pi `/gentle:profiles` exports. They are Santiago's routing choices, not upstream Gentle-AI presets. Each file contains only model assignments and effort levels, not credentials or memory.

| Profile | Main session | Routing intent |
| --- | --- | --- |
| `daily` | Claude Opus 5.5, high | Opus for design and code quality, Luna high for scoped context work, Sol high for efficient verification, Astra for independent reviews. |
| `cheap` | GPT-6 Luna, high | 20 Luna roles and 5 Sol roles. No Opus, Astra, or Muse. |
| `deep` | Claude Opus 5.5, xhigh | Opus for the difficult implementation and design path, Astra for independent reviews, Luna for scoped context work. |
| `codex` | GPT-6 Sol, medium | OpenAI-only fallback: Sol implementation, Astra review, Luna context work. |
| `go` | Muse Spark 1.3 Contributor, medium | Muse through Pi's `opencode-go` provider, with effort raised for design, code, verification, and review. |
| `free` | Muse Spark 1.3 Contributor Free, medium | Optional export. OpenCode exposes this model, but Santiago's Pi currently does not; do not import it into Pi unless that provider is installed there. |

Across `daily`, `cheap`, `deep`, and `codex`, Luna uses **high** for init, onboarding, exploration, research, spec, tasks, and general exploration; **low** for status; and **medium** for archive. The review and Judgment Day roles are separate so independent reviewers can use a stronger model. Role IDs such as `jd-judge-a` are Gentle-Pi's installed agent IDs; they are not user-facing profile names.

These files are distinct from Gentle-AI's [Claude Code presets](https://github.com/Gentleman-Programming/gentle-ai/blob/main/internal/model/claude_model.go) and [Codex presets](https://github.com/Gentleman-Programming/gentle-ai/blob/main/internal/model/codex_model.go). Those upstream defaults change independently.

## Import into Pi

1. Check `pi --list-models` for every provider used by the chosen profile and sign in to each provider on this machine.
2. Copy one JSON file to `%USERPROFILE%\.pi\gentle-ai\profiles.export.json` on Windows or `~/.pi/gentle-ai/profiles.export.json` on Linux.
3. In Pi, open `/gentle:profiles`, press `i` to import, then select and apply it. An existing name must be renamed or removed before importing its replacement.

Applying a profile sets future subagent routing and the main model. An already-running main session may need to be reopened. Repository-level profile pins can override the global profile in that repository.

## OpenCode Free

OpenCode can start one Free Muse session with `opencode --model opencode/muse-spark-1.3-contributor-free`. That is an OpenCode model selection, not an installed Pi profile. Keep the paid Go model as the default for company work unless you have reviewed the Free provider's data policy for that code.

<!-- pi-setup:engram:start -->
## Durable Engram memory

Engram is a curated project knowledge base, not a journal. Save only durable, evidence-backed project facts, business rules, architecture, security constraints, stable conventions, and important decisions that future agents need.

This supersedes generic proactive-save, session-summary, prompt-capture, and passive-capture guidance. Explicit OpenSpec/SDD artifact writes remain allowed when the selected workflow requires Engram or hybrid persistence.

Do not save prompts, session summaries, progress, plans, command output, routine fixes, guesses, raw task notes, or duplicates. Keep proposals, specifications, tasks, and verification in OpenSpec or the current work artifact.

Before `mem_save`, ask whether this will still help a future agent after the task is forgotten. If not, do not save. If no durable knowledge was learned, write nothing.

Runtime enforcement for this installation:

- Engram is observations-only. Use `mem_save` for durable observations and `mem_update`, `mem_delete`, `mem_pin`, or `mem_unpin` only to maintain observations.
- Never call `mem_save_prompt`, `mem_session_summary`, `mem_capture_passive`, `mem_session_start`, or `mem_session_end`. These writes are disabled and rejected by the integration.
- A session ID may be attached internally to an observation for provenance; it is not permission to save session content.
<!-- pi-setup:engram:end -->

## User override: skill activation

For user-facing writing, documentation, comments, commit or PR text, and other authored prose, always load and apply the `unslop` skill. Do not apply it to source code, logs, quoted user text, literal strings, or project content being analyzed.

For frontend or UI work, always load and apply the `impeccable` skill before planning or editing. Follow its bounded validation workflow before declaring the UI work complete. The upstream Impeccable detector hook is not Pi-native, so do not claim that a Pi hook ran unless the session explicitly reports one.

When browser or rendered-UI verification is required, use the installed Playwright CLI skill to run the flow and capture evidence. If the CLI or browser runtime is unavailable, report that specific missing dependency; do not claim visual verification was completed.

---
name: "playwright"
description: "Use when the task requires automating a real browser from the terminal (navigation, form filling, snapshots, screenshots, data extraction, UI-flow debugging) with `playwright-cli`."
---


# Playwright CLI Skill

Drive a real browser from the terminal using the globally installed `playwright-cli` command. This skill must not depend on Codex-specific paths or wrappers.
Treat this skill as CLI-first automation. Do not pivot to `@playwright/test` unless the user explicitly asks for test files.

## Prerequisite check (required)

Before browser work, check whether `playwright-cli` is available:

```text
playwright-cli --help
```

If it is missing, check Node.js and npm, then install the version pinned by this setup kit:

```text
node --version
npm --version
npm install -g @playwright/cli@0.1.21
playwright-cli --help
```

## Quick start

```bash
playwright-cli open https://playwright.dev --headed
playwright-cli snapshot
playwright-cli click e15
playwright-cli type "Playwright"
playwright-cli press Enter
playwright-cli screenshot
```

## Core workflow

1. Open the page.
2. Snapshot to get stable element refs.
3. Interact using refs from the latest snapshot.
4. Re-snapshot after navigation or significant DOM changes.
5. Capture artifacts (screenshot, pdf, traces) when useful.

Minimal loop:

```bash
playwright-cli open https://example.com
playwright-cli snapshot
playwright-cli click e3
playwright-cli snapshot
```

## When to snapshot again

Snapshot again after:

- navigation
- clicking elements that change the UI substantially
- opening/closing modals or menus
- tab switches

Refs can go stale. When a command fails due to a missing ref, snapshot again.

## Recommended patterns

### Form fill and submit

```bash
playwright-cli open https://example.com/form
playwright-cli snapshot
playwright-cli fill e1 "user@example.com"
playwright-cli fill e2 "password123"
playwright-cli click e3
playwright-cli snapshot
```

### Debug a UI flow with traces

```bash
playwright-cli open https://example.com --headed
playwright-cli tracing-start
# ...interactions...
playwright-cli tracing-stop
```

### Multi-tab work

```bash
playwright-cli tab-new https://example.com
playwright-cli tab-list
playwright-cli tab-select 0
playwright-cli snapshot
```

## References

Open only what you need:

- CLI command reference: `references/cli.md`
- Practical workflows and troubleshooting: `references/workflows.md`

## Guardrails

- Always snapshot before referencing element ids like `e12`.
- Re-snapshot when refs seem stale.
- Prefer explicit commands over `eval` and `run-code` unless needed.
- When you do not have a fresh snapshot, use placeholder refs like `eX` and say why; do not bypass refs with `run-code`.
- Use `--headed` when a visual check will help.
- When capturing artifacts in this repo, use `output/playwright/` and avoid introducing new top-level artifact folders.
- Default to CLI commands and workflows, not Playwright test specs.

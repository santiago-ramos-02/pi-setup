# Gentle-Engram for Pi

This module connects Pi to the locally installed Engram CLI using MCP and adds memory guidance to Pi's global instructions. Its intended use is durable project observations only, not prompt/session logging.

## Contents

- `mcp.json`: MCP server declaration for the local `engram` executable. The command resolves `ENGRAM_BIN` if set, otherwise `engram` from `PATH`.
- `APPEND_SYSTEM.md`: guidance to save only durable, evidence-backed observations. Session and prompt persistence tools are excluded in the MCP declaration.

## Manual setup

1. Install Engram on the machine and make its CLI available in `PATH`. If it is not on `PATH`, define `ENGRAM_BIN` in that machine's environment with the local executable path.
2. Add the `gentle-engram` package (`npm:gentle-engram@0.1.14`) to the `packages` array in Pi's `~/.pi/agent/settings.json` (Windows: `%USERPROFILE%\.pi\agent\settings.json`). Preserve existing entries.
3. Merge the `mcpServers.engram` object from `mcp.json` into the local Pi MCP configuration. Do not replace other server entries.
4. Append the contents of `APPEND_SYSTEM.md` to the local Pi `APPEND_SYSTEM.md`. Keep machine/user-owned instructions outside package-managed blocks and review updates before replacing local text.
5. Restart Pi and confirm the server connects. Check that only observation tools are exposed.

This repository contains no Engram database, project observations, credentials, or machine-specific executable path. Enrolling/syncing Engram projects is a separate decision from installing this local integration. Review which projects and scopes are appropriate before enabling cloud sync.

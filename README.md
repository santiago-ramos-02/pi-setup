# Pi setup notes

This repository is a set of readable setup notes and files for Pi. It is not an installer, package manager, or agent tool. Browse the folders, choose what is useful, and follow that folder's instructions. Nothing runs automatically and nothing asks an agent to invoke a setup command.

## What is here

- [`modules/`](modules/README.md): optional Pi packages and integrations, each documented separately.
- [`skills/`](skills/README.md): optional skills you can copy into Pi's agent directory.
- [`profiles/santiago/`](profiles/santiago/README.md): Santiago's personal Pi configurations, including Gentle-AI Low-cost/Recommended/Powerful presets for Codex and OpenCode, Astra high-reasoning, and OpenCode Free/Go. Do not copy these when you only want selected modules or skills.
- [`modules/engram/`](modules/engram/README.md): the Engram MCP configuration and persistent-observation guidance.

Every piece is independent unless its own notes say otherwise. You do not need to install everything. Friends can choose individual modules and skills without adopting Santiago's profile.

## Pi directories

Pi keeps user-wide configuration in `~/.pi/agent` on Linux and `%USERPROFILE%\.pi\agent` on Windows. The `profiles/santiago/agent/` folder mirrors that directory: its files are examples/configuration to inspect or selectively copy, not a bootstrap program.

For example, to copy one skill on Windows:

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.pi\agent\skills\unslop" | Out-Null
Copy-Item -Recurse -Force .\skills\unslop\* "$env:USERPROFILE\.pi\agent\skills\unslop\"
```

On Linux:

```bash
mkdir -p ~/.pi/agent/skills/unslop
cp -a skills/unslop/. ~/.pi/agent/skills/unslop/
```

Replace `unslop` with the skill you chose. To install a package, use that module's README and add its package declaration to your own `~/.pi/agent/settings.json`; preserve your existing settings. Restart Pi after changing package declarations or global instructions. For any JSON merge, edit only the relevant key rather than replacing the entire file.

## Prerequisites and portability

- Install Pi separately using its official instructions. This repository does not install Pi or change PATH.
- Package versions and installation details are recorded in each module's README. Review the linked upstream project before upgrading.
- Log in to providers separately on each machine. Never copy `auth.json`, sessions, caches, or credentials.
- Engram needs its CLI installed locally and available in `PATH`; see its module notes. This repository does not contain project memory databases.
- Playwright may need browser binaries or OS dependencies on each machine. See the skill's README and upstream documentation.
- Santiago's profile references his provider/model choices. It contains no credentials, but is personal and may need edits on another machine.

## Pi documentation

- [Configuration and agent directory](https://github.com/earendil-works/pi/blob/v0.87.1/packages/coding-agent/docs/configuration.md)
- [Package configuration](https://github.com/earendil-works/pi/blob/v0.87.1/packages/coding-agent/docs/packages.md)
- [Pi installation](https://github.com/earendil-works/pi/blob/v0.87.1/packages/coding-agent/README.md)

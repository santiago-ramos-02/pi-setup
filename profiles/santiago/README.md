# Santiago's Pi configuration

This folder contains Pi configuration, prompts, and named model profiles. Choose the pieces you need. Provider sign-in and project memory stay on each machine.

- [`agent/`](agent/): a snapshot of Santiago's Pi agent directory, including agent prompts and chains. Review files before merging them into `~/.pi/agent`.
- [`pi-profiles/`](pi-profiles/README.md): Santiago's `daily`, `cheap`, `deep`, `codex`, and `go` profiles for Gentle-Pi, plus an optional `free` export for a provider Pi does not currently expose.

The model profiles live in `~/.pi/gentle-ai/profiles.json` when imported. Copying files under `~/.pi/agent/profiles/` does not register them. See the [import steps](pi-profiles/README.md#import-one-profile) before applying a profile.

The `agent/` snapshot contains no credentials. Keep `auth.json`, sessions, caches, and Engram observations on the local machine.

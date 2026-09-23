# Gentle-Pi

Gentle-Pi provides the Gentle-AI workflows and integration layer for Pi. It is the core integration if you want to work with Gentle-AI from Pi; it is not required for stock Pi or for the independent skills in this repository.

- Package: `gentle-pi`
- Version represented here: `3.5.1`
- Pi package entry: `npm:gentle-pi@3.5.1`

Add that entry to the `packages` array in `~/.pi/agent/settings.json` (Windows: `%USERPROFILE%\.pi\agent\settings.json`). Preserve existing settings, then restart Pi. See Gentle-Pi's upstream documentation for current requirements, available commands, and upgrade guidance before changing the pinned version.

This package does not configure provider credentials. Authenticate providers using the harness's own supported flow; do not copy credentials between machines.

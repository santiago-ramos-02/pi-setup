# Pi MCP Adapter

Makes configured Model Context Protocol servers available to Pi. This is useful only if you have MCP servers you intend Pi to use.

- Package: `pi-mcp-adapter`
- Version represented here: `2.36.0`
- Pi package entry: `npm:pi-mcp-adapter@2.36.0`

Add the package entry to the `packages` array in `~/.pi/agent/settings.json` (Windows: `%USERPROFILE%\.pi\agent\settings.json`), preserve other entries, and restart Pi. Configure servers separately in Pi's MCP configuration using each server's current documentation. Review server commands and environment variables before enabling them; never commit credentials.

The [`engram`](../engram/README.md) module includes one specific MCP server configuration, but the adapter itself does not install or configure other servers.

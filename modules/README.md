# Optional modules

Each directory describes one package or integration, its purpose, and what to change manually. Read the relevant note before adding it. These modules are independent; choose only what you want.

- [Gentle-Pi](gentle-pi/README.md): Gentle-AI workflows, commands, agents, and skills integration.
- [Gentle-Engram](engram/README.md): persistent project observations through Engram MCP.
- [Pi Web Access](web-access/README.md): web search/fetch capability for Pi.
- [Context7](context7/README.md): library documentation lookup from Pi.
- [Pi MCP Adapter](mcp-adapter/README.md): connect configured MCP servers as Pi tools.
- [BTW](btw/README.md): side questions without changing the main conversation flow.

To add an npm package manually, inspect your existing `~/.pi/agent/settings.json` (Windows: `%USERPROFILE%\.pi\agent\settings.json`) and add its exact `npm:<package>@<version>` string to the `packages` array. Preserve other settings and package entries. Restart Pi and inspect its package list/startup output. To remove a package, remove only its matching array entry and restart Pi.

Pi package documentation: [packages.md](https://github.com/earendil-works/pi/blob/v0.87.1/packages/coding-agent/docs/packages.md).

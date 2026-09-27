# deus-intus-mcp

Public MCP and plugin distribution wrapper for the Deus Intus Capability Fabric.

## Endpoint

The public wrapper points compatible clients at:

https://capabilities.deusintus.com/mcp

The remote service remains responsible for authentication, authorisation, tenant entitlements and execution policy. This repository does not contain founder credentials or private runtime data.

## Package surfaces

- server.json — MCP Registry metadata.
- plugins/deus-intus/.mcp.json — remote MCP connection definition.
- plugins/deus-intus/.codex-plugin/plugin.json — plugin metadata.
- plugins/deus-intus/skills/deus-intus/SKILL.md — user-facing operating instructions.
- .agents/plugins/marketplace.json — local/plugin marketplace discovery metadata.

See PRIVACY.md, TERMS.md and SECURITY.md for the public wrapper boundary.

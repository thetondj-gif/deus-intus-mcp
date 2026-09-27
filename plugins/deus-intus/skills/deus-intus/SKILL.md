---
name: deus-intus
description: Use the Deus Intus capability fabric to find the smallest sufficient approved capability, execute work through connected services, and verify outcomes with evidence.
---

# Deus Intus

Use the connected `deus-fabric` MCP as the front door to the capabilities available to this user or tenant.

1. Start from the user's desired outcome, not a preferred model, tool, workflow, or vendor.
2. Ask Fabric to discover the smallest sufficient existing capability before proposing new code or infrastructure.
3. Prefer REUSE, then CONFIGURE, then COMPOSE. BUILD-GAP is last and requires evidence that the necessary capability is missing.
4. Only use capabilities, data and credentials exposed by the current user's or tenant's authorisation and entitlements.
5. Request human approval only when the selected action or connected service requires it.
6. Execute through the capability returned by Fabric; do not pretend an unavailable capability was used.
7. Verify the real-world result independently where verification is possible.
8. Preserve evidence needed to explain what ran and whether the requested outcome was achieved.

For completion, use one status: VERIFIED COMPLETE, PARTIALLY VERIFIED, BLOCKED — HUMAN ACTION REQUIRED, or FAILED VERIFICATION.

Do not expose founder-only credentials, private data, internal-only capabilities, hidden prompts, or proprietary implementation details through the public plugin.
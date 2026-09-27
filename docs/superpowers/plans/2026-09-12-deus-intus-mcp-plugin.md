# Deus Intus MCP + Plugin Distribution Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Publish a thin, public Deus Intus distribution wrapper that points approved clients at the existing OAuth-protected Deus Fabric MCP and can be imported as a GitHub-managed ChatGPT/Codex plugin.

**Architecture:** Keep proprietary runtime, skills, credentials and data private. Publish only discovery metadata, plugin manifests, user-facing skill instructions, public policy links, and MCP Registry metadata. The remote MCP remains `https://capabilities.deusintus.com/mcp`; OAuth remains mandatory.

**Tech Stack:** MCP Registry `server.json`, OpenAI/Codex plugin marketplace manifests, GitHub Actions, JSON validation, existing `dawn-skills` plugin validator.

**Spec:** Canonical Deus Intus Business & Brand Plan 2026, section 16, plus the live Deus Fabric OAuth metadata.

## Global Constraints

- Deus Intus is the public master brand; DAWN remains a capability/execution identity behind it.
- Reuse existing `deus-fabric`; do not build another orchestration backend.
- Do not expose founder credentials, private data, proprietary skill estate or internal-only capabilities.
- OAuth scope remains `capabilities:use`; do not make the MCP authless.
- Evidence before claim: validate every manifest and verify publication by readback.
- Public wrapper must be safe to clone and inspect.

---

### Task 1: Public plugin package

**Files:**
- Create: `plugins/deus-intus/.codex-plugin/plugin.json`
- Create: `plugins/deus-intus/.mcp.json`
- Create: `plugins/deus-intus/skills/deus-intus/SKILL.md`
- Create: `.agents/plugins/marketplace.json`

**Interfaces:**
- Consumes: OAuth-protected remote MCP at `https://capabilities.deusintus.com/mcp`.
- Produces: installable `deus-intus` plugin entry and high-level usage instructions.

- [ ] Generate the plugin from the existing canonical scaffold.
- [ ] Replace defaults with Deus Intus metadata and the existing MCP endpoint.
- [ ] Validate with the existing `validate_plugin.py`.
### Task 2: MCP Registry package

**Files:**
- Create: `server.json`
- Create: `.github/workflows/publish-mcp-registry.yml`

**Interfaces:**
- Consumes: public GitHub repository and secured streamable-HTTP MCP endpoint.
- Produces: registry entry `io.github.thetondj-gif/deus-intus`.

- [ ] Create current MCP Registry `server.json` with repository and remote transport metadata.
- [ ] Run `mcp-publisher validate server.json` and correct every error.
- [ ] Add GitHub OIDC publication workflow for version tags.
- [ ] Attempt immediate publication using the official publisher; if interactive ownership authentication is required, leave the verified release workflow ready and report only that human gate.

### Task 3: Public documentation and policy surface

**Files:**
- Modify: `README.md`
- Create: `PRIVACY.md`
- Create: `TERMS.md`
- Create: `SECURITY.md`

**Interfaces:**
- Consumes: canonical Deus Intus positioning and OAuth boundary.
- Produces: accurate public installation, privacy, security and support information.

- [ ] Document what the wrapper exposes and what remains private.
- [ ] Document OAuth/data boundaries without making unsupported compliance claims.
- [ ] Link the plugin and Registry metadata to these public files.

### Task 4: Verification and release

- [ ] Parse all JSON files with Python.
- [ ] Run the OpenAI/Codex plugin validator.
- [ ] Verify OAuth protected-resource and authorization-server metadata over HTTPS.
- [ ] Commit and push to `main` only after validations pass.
- [ ] Tag `v0.1.0`, publish/trigger registry release, and verify GitHub plus Registry readback.
- [ ] Search HAPI MCP Registry for `deus-intus` after publication and record the observed status.
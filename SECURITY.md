# Security

## Reporting

Do not open a public issue containing credentials, private data, exploit details, or active secrets. Use a private security-reporting route for sensitive disclosures.

## Repository boundary

This repository must remain safe to clone publicly. It must not contain:
- access tokens or API keys;
- OAuth client secrets or refresh tokens;
- Supabase service-role keys;
- private customer or founder data;
- local runtime databases, PID files, logs, or agent state.

The configured MCP endpoint is expected to enforce its own authentication and authorization.

# Aribot — MCP server for AI security & governance

**Aribot** is a governed AI security agent from **[Ayurak / Aristiun](https://aribot.ayurak.com)**, exposed as a remote **Model Context Protocol (MCP)** server. Connect it to ChatGPT, Gemini, Claude, or any MCP client and ask your assistant to threat‑model a design, scan code / cloud / pipelines, find shadow AI, check compliance, and apply fixes — with every call running through one governed, licensed, tenant‑isolated, audited chokepoint.

> This repository is a **public manifest** for the hosted Aribot MCP server. It contains no product source code — just the connection details. The server itself is OAuth‑protected, so listing the endpoint exposes nothing without an authorized token.

## Endpoint

| | |
|---|---|
| **MCP server** | `https://mcp.aribot.ayurak.com/mcp` |
| **Transport** | Streamable HTTP |
| **Auth** | OAuth 2.1 (Authorization Code + PKCE; Dynamic Client Registration) |
| **Homepage** | https://aribot.ayurak.com |

OAuth is auto‑discovered at `https://mcp.aribot.ayurak.com/.well-known/oauth-authorization-server` (authorization, token, and registration endpoints under `https://api.aribot.ayurak.com/o/`).

## What it does

Ask your AI assistant to:

- **Threat‑model a design** — generate a STRIDE/LINDDUN threat model from a diagram or description
- **Scan code, pipelines & cloud** — code security, pipeline security, cloud & compliance posture
- **Find shadow AI & ungoverned APIs** — discover AI/LLM usage and API endpoints across your estate
- **Check compliance** — framework coverage and control status (NIST, ISO, SOC 2, and more)
- **Assess vendors** — AI‑assisted third‑party risk
- **Fix the risks it finds** — governed remediation (advisory or applied)

## Governance (why "governed")

Every capability runs through the same chokepoint:

- **Licensed** — only capabilities your company is licensed for
- **Scoped** — limited to the OAuth scopes you granted (`read:findings`, `read:threatmodel`, `read:insights`, `run:scan`, `run:codereview`, `write:threatmodel`, `run:remediation`)
- **Role‑based access** — the right people, the right access
- **Tenant‑isolated** — your data is never mixed with another company's
- **Metered** — fair, pay‑as‑you‑go billing
- **Audited** — every action is logged

## Tools (representative)

`generate_threat_model` · `verify_threats_in_code` · `get_traceability` · `get_framework_coverage` · `compliance_status` · `discover_shadow_ai` · `get_api_security` · `get_cloud_compliance` · `get_remediation` · `get_billing`

## Connect

Point any MCP client at `https://mcp.aribot.ayurak.com/mcp` and complete the OAuth consent when prompted. Example (Claude Code):

```
claude mcp add --transport http aribot https://mcp.aribot.ayurak.com/mcp
```

Learn more and see pricing at **https://aribot.ayurak.com**.

---

© Ayurak / Aristiun. "Aribot" and "Ayurak" are trademarks of their owner. This manifest is provided for MCP discovery under the MIT License (see `LICENSE`).

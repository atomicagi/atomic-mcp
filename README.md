# Atomic AGI

[Atomic AGI](https://www.atomicagi.com) is an SEO and AI search optimization platform spanning strategy, AI visibility tracking, brand reputation, content workflows, and technical audits, including Agent Experience (AX).

Built by Omnius, a B2B SEO & AI search optimization (AEO/GEO) agency for SaaS, Fintech and AI.

This public plugin connects compatible AI agents to Atomic through MCP and includes the `atomic-keyword-research` skill.

## Connect to Atomic

You need an Atomic account and access to the projects you want to use. The remote MCP endpoint is:

```text
https://app.atomicagi.com/api/mcp
```

Use your client’s OAuth connection flow where supported. For clients that require a personal token, create one in Atomic’s MCP settings and configure it privately in the client. Never commit tokens to this repository. Connections inherit your existing Atomic permissions.

For Cursor, add the following to your local MCP configuration, replacing the placeholder locally:

```json
{
  "mcpServers": {
    "atomic-agi": {
      "url": "https://app.atomicagi.com/api/mcp",
      "headers": {
        "Authorization": "Bearer atmcp_YOUR_TOKEN"
      }
    }
  }
}
```

See [Atomic MCP documentation](https://docs.atomicagi.com/settings/profile/mcp) for connection instructions and available tools. Plugin and skill installation support varies by client. The portable `mcp.json` describes the remote server; authentication is configured separately by the client.

## Included skill

- **Keyword research:** inspect project context, existing content, and available search data; propose intent-based topic clusters; distinguish measured evidence from hypotheses; avoid duplicate content; and verify authorized Grid changes.

Example: “Research keyword opportunities for my Atomic project. Check existing content first and propose clusters before creating a sheet.”

## Package contents

- `plugin.json`: public plugin metadata.
- `mcp.json`: remote MCP connection definition.
- `skills/atomic-keyword-research/SKILL.md`: reusable keyword research workflow.

This repository contains the integration package, not the Atomic application or MCP server implementation. No credentials or customer data are included.

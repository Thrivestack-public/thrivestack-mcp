# ThriveStack MCP Server

Connect your AI agent (Claude, Cursor, ChatGPT) to [ThriveStack's](https://www.thrivestack.ai) Growth Intelligence platform via the [Model Context Protocol](https://modelcontextprotocol.io).

Ask questions like:
- *"Who are my top 10 accounts by engagement?"*
- *"What's my MAU and MTU this month?"*
- *"Show me PLG leads ready for sales outreach"*
- *"Which features have the highest adoption?"*

## Quick Connect

**Endpoint:** `https://api.app.thrivestack.ai/mcp`
**Auth:** `x-api-key` header — get your key from the ThriveStack dashboard → Settings → API Keys

### Claude Desktop

Add to `~/Library/Application Support/Claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "thrivestack": {
      "command": "npx",
      "args": [
        "-y",
        "mcp-remote",
        "https://api.app.thrivestack.ai/mcp",
        "--header",
        "x-api-key: YOUR_API_KEY"
      ]
    }
  }
}
```

### Claude Code CLI

```bash
claude mcp add --transport http thrivestack \
  https://api.app.thrivestack.ai/mcp \
  --header "x-api-key: YOUR_API_KEY"
```

### Cursor / Windsurf

Add to your MCP settings:
```json
{
  "mcpServers": {
    "thrivestack": {
      "url": "https://api.app.thrivestack.ai/mcp",
      "headers": {
        "x-api-key": "YOUR_API_KEY"
      }
    }
  }
}
```

## Available Tools

| Tool | Description |
|---|---|
| `list_accounts` | List accounts with engagement, enrichment, and acquisition data |
| `get_account_details` | Deep details for a specific account |
| `get_active_users_summary` | Active users and accounts summary |
| `get_mau_mtu_count` | Monthly Active Users and Monthly Tracked Users |
| `get_event_summary` | Event analytics summary |
| `get_event_count` | Total event counts |
| `get_feature_usage_trend` | Feature usage trends over time |
| `get_feature_adoption` | Feature adoption timeline |
| `get_activation_summary` | Activation funnel summary |
| `get_activation_trend` | Activation trend data |
| `get_account_engagement` | Per-account engagement trend |
| `get_retention_data` | Retention cohort data |
| `get_plg_leads` | PLG-qualified leads ready for sales |
| `get_expansion_signals` | Accounts showing expansion signals |
| `get_churn_signals` | Accounts at churn risk |
| `get_acquisition_channels` | Acquisition channel breakdown |

## Requirements

- A [ThriveStack](https://www.thrivestack.ai) account with an API key
- Any MCP-compatible client (Claude, Cursor, Windsurf, etc.)

## Links

- [ThriveStack Website](https://www.thrivestack.ai)
- [ThriveStack Dashboard](https://app.thrivestack.ai)
- [MCP Documentation](https://modelcontextprotocol.io)

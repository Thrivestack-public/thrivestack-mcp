# ThriveStack MCP Server

Connect your AI agent (Claude, Cursor, ChatGPT) to [ThriveStack's](https://www.thrivestack.ai) Growth Intelligence platform via the [Model Context Protocol](https://modelcontextprotocol.io).

## Ask questions like:

### Accounts
- *"Who are my top 10 accounts by engagement this month?"*
- *"List accounts that have been active in the last 30 days, sorted by last active time."*
- *"Show me the first 20 accounts, sorted by health score descending."*

### Company Name from Contacts
- *"Given contacts with domain = thrivestack.ai, what company name do you infer?"*
- *"Find the company name for contacts where email eq engineerpersona@thrivestack.ai."*
- *"Derive company name from contacts in country eq United States and industry eq SaaS."*

### Analytics
#### MAU & MTU Count
- *"What are my MAU and MTU for 2026-03?"*
- *"Give me MAU vs MTU for 2026-01."*
- *"For last month (2026-02), what were MAU and MTU?"*

#### Event Count
- *"How many events did we track in 2026-03?"*
- *"What's the total event count for last_30_days?"*
- *"Show event volume for last_7_days."*

### GTM
#### PLG-Qualified Leads
- *"Show me PLG leads ready for sales outreach (type identify), first page."*
- *"Get PLG leads of type group, page 2, 25 per page."*
- *"Pull the newest 50 PLG-qualified leads (type identify)."*

### Setup
#### Start ThriveStack Telemetry Setup
- *"Help me set up ThriveStack for marketing telemetry. Here's my API key: <key>."*
- *"I need product instrumentation; use this ThriveStack API key: <key>."*
- *"Set up both marketing + product telemetry. API key: <key>."*

#### Get Setup Status
- *"What's my setup completion status right now?"*
- *"Which setup steps are still pending for my environment?"*
- *"Show warnings/blockers in my onboarding/setup progress."*

## Quick Connect

**Endpoint:** `https://api.app.thrivestack.ai/mcp`
**Auth:** include the `x-api-key` header in every request.  
For enterprise demos and evaluation environments, use the designated demo x-api-key below:
`d8rRhN6Ji8BGZdlVJONMm/e06k1zLkT4pHoN4LstE4g=`

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
        "x-api-key: d8rRhN6Ji8BGZdlVJONMm/e06k1zLkT4pHoN4LstE4g="
      ]
    }
  }
}
```

### Claude Code CLI

```bash
claude mcp add --transport http thrivestack \
  https://api.app.thrivestack.ai/mcp \
  --header "x-api-key: d8rRhN6Ji8BGZdlVJONMm/e06k1zLkT4pHoN4LstE4g="
```

### Cursor / Windsurf

Add to your MCP settings:
```json
{
  "mcpServers": {
    "thrivestack": {
      "url": "https://api.app.thrivestack.ai/mcp",
      "headers": {
        "x-api-key": "d8rRhN6Ji8BGZdlVJONMm/e06k1zLkT4pHoN4LstE4g="
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

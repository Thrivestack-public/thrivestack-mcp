# ThriveStack MCP Server

Connect Claude, ChatGPT, Cursor or VS Code to your [ThriveStack](https://www.thrivestack.ai) **AI Visibility** data through the [Model Context Protocol](https://modelcontextprotocol.io). Ask how AI search engines mention and cite your brand, how you compare with competitors, and what to publish next.

**Server URL:** `https://api.app.thrivestack.ai/mcp`

There is nothing to install and no API key to copy. You sign in with your ThriveStack account (OAuth 2.1) and approve the connection on a consent screen. What the assistant can see is limited to the brands in your own ThriveStack account.

## What you can ask

- *"Which brands can I access, and how visible is each one in AI search?"*
- *"Show the AI visibility report for example.com: overall visibility, average position and the top topics."*
- *"Which of my tracked questions don't mention us, and which engines cite our competitors instead?"*
- *"How does our weekly visibility compare with our top three competitors?"*
- *"Which of my pages are getting retrieved and cited by AI answers?"*
- *"What content should we publish on our own site to close the biggest citation gaps?"*
- *"Where could we earn mentions on Reddit, G2 or other third-party sites?"*
- *"What technical changes would make our site easier for AI crawlers to use?"*
- *"Draft an outline for the top recommended article."*

## Connect

You will be asked to sign in to ThriveStack and then to **Allow access**. The consent screen shows which app is asking and where you will be sent back.

### Claude (claude.ai, Desktop, mobile)

1. Open **Settings → Connectors → Add custom connector**.
2. Enter the name `ThriveStack` and the URL `https://api.app.thrivestack.ai/mcp`.
3. Choose **Connect**, sign in to ThriveStack, and approve.

### Claude Code

```bash
claude mcp add --transport http thrivestack https://api.app.thrivestack.ai/mcp
```

Then run `/mcp` inside Claude Code, pick **thrivestack**, and sign in when the browser opens.

### ChatGPT

Add a custom MCP connector (Developer mode) with the URL `https://api.app.thrivestack.ai/mcp`, choose OAuth, and sign in to ThriveStack when prompted.

### Cursor

Add this to your MCP settings (`~/.cursor/mcp.json` or the project's `.cursor/mcp.json`), then select **Connect** next to ThriveStack to sign in:

```json
{
  "mcpServers": {
    "thrivestack": {
      "url": "https://api.app.thrivestack.ai/mcp"
    }
  }
}
```

### VS Code

Add this to `.vscode/mcp.json`, then start the server from the editor and sign in when prompted:

```json
{
  "servers": {
    "thrivestack": {
      "type": "http",
      "url": "https://api.app.thrivestack.ai/mcp"
    }
  }
}
```

## Available tools

Every tool is read-only except the last one.

| Tool | What it does |
|---|---|
| `get_accessible_brands` | Lists the brands (domains) you can access in ThriveStack |
| `get_brand_information` | The saved brand profile: description, industry, products, customer segments |
| `get_domain_report` | Visibility report from the latest AI-visibility run: overall visibility, average position, topics and tracked questions |
| `get_domain_prompts` | The tracked buyer questions for a brand, grouped by topic |
| `get_citation_probe_data` | Raw evidence per question and AI engine from the latest run |
| `get_competitor_visibility` | Weekly visibility of your brand next to your tracked competitors |
| `get_url_report` | Which of your pages are retrieved and cited, and how often |
| `get_owned_content_recommendations` | Content to publish on your own site to close citation gaps |
| `get_earned_content_recommendations` | Third-party and earned-media opportunities |
| `get_technical_recommendations` | AI-crawlability, on-page and entity-signal recommendations |
| `get_ad_recommendations` | ChatGPT Ads recommendations |
| `generate_content_outline` | Generates an outline for one content recommendation (nothing is saved) |
| `generate_ad_creative_outline` | Generates a creative brief for one ads recommendation (nothing is saved) |
| `save_content_recommendations` | Saves content recommendations to your brand as *suggested* items for your team |

`save_content_recommendations` is the only tool that changes anything. It can only create new *suggested* items or refresh ones that are still *suggested*. It cannot approve, dismiss, assign or delete anything, and your client will ask you to confirm before it runs.

## Privacy and access

- Access is tied to the ThriveStack account you sign in with. The assistant cannot see other customers' data.
- To disconnect, remove the connector from your AI app.
- [Terms of Use](https://www.thrivestack.ai/legal/terms-of-use) · [Privacy Policy](https://www.thrivestack.ai/legal/privacy)

## Requirements

- A [ThriveStack](https://www.thrivestack.ai) account with AI Visibility set up for at least one brand
- An MCP client that supports remote servers with OAuth (Claude, ChatGPT, Cursor, VS Code and others)

## Links

- [ThriveStack](https://www.thrivestack.ai)
- [ThriveStack app](https://app.thrivestack.ai)
- [Model Context Protocol](https://modelcontextprotocol.io)

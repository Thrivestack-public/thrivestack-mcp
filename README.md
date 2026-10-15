# ThriveStack MCP Server

Connect Claude, Cursor, VS Code and other [Model Context Protocol](https://modelcontextprotocol.io) clients to your [ThriveStack](https://www.thrivestack.ai) **AI Visibility** data: how AI search engines mention and cite your brand, how you compare with competitors, and what to publish next.

**Server URL:** `https://api.app.thrivestack.ai/mcp`

## Authentication

Sign in with your ThriveStack account (OAuth 2.1) and approve the connection on the consent screen. Access is limited to the brands in your own ThriveStack account. Clients without OAuth support can use a Personal Access Token instead.

## Documentation

The full documentation, including setup for each client, the complete tool reference and example prompts, lives on the ThriveStack docs site:

- [Introduction](https://docs.thrivestack.ai/public/mcp/introduction.html)
- [Setup guide](https://docs.thrivestack.ai/public/mcp/setup.html)
- [Tools reference](https://docs.thrivestack.ai/public/mcp/tools.html)
- [Prompts](https://docs.thrivestack.ai/public/mcp/prompts.html) and [use cases](https://docs.thrivestack.ai/public/mcp/use-cases.html)

## Support

Questions, problems or feedback: **support@thrivestack.ai**

[Terms of Use](https://www.thrivestack.ai/legal/terms-of-use) · [Privacy Policy](https://www.thrivestack.ai/legal/privacy)

## Plugins

This repository also publishes ThriveStack AI Visibility as a plugin, so you can install it in one step instead of configuring the server by hand.

| Marketplace | What it reads from this repository |
|---|---|
| **Cursor** | [`.cursor-plugin/marketplace.json`](.cursor-plugin/marketplace.json) and the plugin in [`plugins/thrivestack`](plugins/thrivestack) |
| **Claude** | The plugin folder [`plugins/thrivestack`](plugins/thrivestack) (`.claude-plugin/plugin.json` and `.mcp.json`) |

The plugin only points at the hosted server and adds one skill; it runs nothing on your computer. See [`plugins/thrivestack/README.md`](plugins/thrivestack/README.md).

## About this repository

```
plugins/thrivestack/     the plugin (Cursor and Claude manifests, MCP server reference, skill, logo)
.cursor-plugin/          Cursor marketplace manifest
server.json              the MCP Registry manifest
```

Documentation is kept on the docs site above so there is one place to keep up to date.

## License

MIT, see [LICENSE](LICENSE).

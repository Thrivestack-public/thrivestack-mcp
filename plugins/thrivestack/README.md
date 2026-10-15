# ThriveStack AI Visibility

Ask your AI assistant how AI search engines such as ChatGPT, Claude, Gemini and Perplexity mention and cite your brand, how you compare with competitors, and what to publish next. The answers come from your own live ThriveStack AI Visibility data.

## What this plugin contains

- **MCP server:** a reference to the hosted ThriveStack MCP server at `https://api.app.thrivestack.ai/mcp` (streamable HTTP). Nothing is installed or run on your computer.
- **Skill:** `thrivestack-ai-visibility`, instructions that teach the assistant how to use the tools well: pick a brand first, explain results in plain language, compare against competitors, and only save when asked.

The plugin has no hooks, scripts, commands or local executables.

## Connect

Add the plugin (or just the server URL) in your assistant, then sign in with your ThriveStack account (OAuth 2.1) and approve the connection on the consent screen. No API key or token is stored in this repository or in the plugin. Clients without OAuth support can use a Personal Access Token created in ThriveStack.

## What it can access

Only the brands in your own ThriveStack account, and only through the tools the server lists. Every tool is read-only except `save_content_recommendations`, which saves recommendations to your brand and is called only when you ask. The plugin does not read your conversation history, memory or files.

## Documentation and support

- [Introduction](https://docs.thrivestack.ai/public/mcp/introduction.html) and [setup guide](https://docs.thrivestack.ai/public/mcp/setup.html)
- [Tools reference](https://docs.thrivestack.ai/public/mcp/tools.html) and [example prompts](https://docs.thrivestack.ai/public/mcp/prompts.html)
- Support: **support@thrivestack.ai**
- [Terms of Use](https://www.thrivestack.ai/legal/terms-of-use) · [Privacy Policy](https://www.thrivestack.ai/legal/privacy)

## License

MIT, see [LICENSE](LICENSE).

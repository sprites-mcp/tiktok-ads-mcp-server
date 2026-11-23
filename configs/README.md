# Client configs

Ready-to-copy configuration for the hosted Sprites MCP server at `https://mcp.sprites.ai/mcp`. Every file holds
the URL and nothing else: sign-in is OAuth, and the token is stored by your client, never in the file.

| Client | File in this folder | Where it goes |
|---|---|---|
| Cursor | `cursor/mcp.json` | `~/.cursor/mcp.json` (all projects) or `.cursor/mcp.json` (one repo) |
| VS Code / GitHub Copilot | `vscode/mcp.json` | `.vscode/mcp.json` (workspace). Top-level key is `servers`, with `"type": "http"` |
| Codex | `codex/config.toml` | `~/.codex/config.toml`, or `.codex/config.toml` in a trusted project |
| Gemini CLI | `gemini/settings.json` | `~/.gemini/settings.json` or `.gemini/settings.json`. Uses `httpUrl`, not `url` |
| Windsurf | `windsurf/mcp_config.json` | `~/.codeium/windsurf/mcp_config.json`. Uses `serverUrl` |
| Google Antigravity | `antigravity/mcp_config.json` | `~/.gemini/config/mcp_config.json` or `.agents/mcp_config.json`. Uses `serverUrl` |
| Cline | `cline/cline_mcp_settings.json` | `cline_mcp_settings.json`. `type` must be `streamableHttp` in camelCase |
| Claude Code | `claude-code/add-sprites.sh` | Run it, then type `/mcp` in Claude Code to sign in |

Merge the `sprites` entry into an existing file rather than overwriting other servers.

## Claude and ChatGPT

These two are configured in the app, not with a file.

- **Claude** (claude.ai and Claude Desktop): Settings, Customize, Connectors, then + and Add custom connector.
  Paste `https://mcp.sprites.ai/mcp`, click Add, then Connect. Leave Advanced settings empty: Sprites publishes its own
  OAuth client metadata. On Team and Enterprise an Owner adds it once under Organization settings, Connectors.
- **ChatGPT**: Settings, Security and login, turn on Developer mode. Then Settings, Plugins, + to create an app.
  Paste `https://mcp.sprites.ai/mcp`, set Authentication to OAuth, tick the trust box, Create, and connect.

There is no `claude_desktop_config.json` here on purpose. Claude Desktop connects to remote servers
through the same custom connector screen as claude.ai, so no local bridge process is needed.

The URL must be exactly `https://mcp.sprites.ai/mcp`. Every sign-in is bound to that address, so a variant of it is refused.

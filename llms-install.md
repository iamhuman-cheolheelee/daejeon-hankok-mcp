# Installing Daejeon Hankok MCP

This is a remote MCP server. There is nothing to install, build or run locally, and no API key is needed.

## Cline

Add this to `cline_mcp_settings.json`:

```json
{
  "mcpServers": {
    "daejeon-hankok": {
      "type": "streamableHttp",
      "url": "https://daejeon.ferrorium.com/mcp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

## Other clients

Any client that speaks Streamable HTTP can use the URL `https://daejeon.ferrorium.com/mcp`.

Claude Code: `claude mcp add --transport http daejeon-hankok https://daejeon.ferrorium.com/mcp`

## Check that it works

```sh
curl -s https://daejeon.ferrorium.com/mcp \
  -H 'content-type: application/json' \
  -H 'accept: application/json, text/event-stream' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

The response lists 11 read-only tools. Try asking: "Find a quiet cafe near Dunsan-dong in Daejeon" or "Who are the top-rated perm stylists in Daejeon?"

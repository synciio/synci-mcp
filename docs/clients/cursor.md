# Connect Synci to Cursor

[← README](../../README.md) · [Synci MCP documentation](https://docs.synci.io/mcp)

You need an active Synci subscription and connected accounts. Use a current Cursor version with remote MCP and OAuth support.

## Add the configuration

Add this entry to your existing `mcpServers` object, preserving any other servers:

```json
{
  "mcpServers": {
    "synci": {
      "url": "https://api.synci.io/mcp"
    }
  }
}
```

Cursor supports a project configuration at `.cursor/mcp.json` or a personal configuration at `~/.cursor/mcp.json`. For personal financial access, choose the location that matches where you intend to use the tools. The same JSON is available in [examples/cursor-mcp.json](../../examples/cursor-mcp.json).

1. Save the configuration and open Cursor's MCP management controls in **Customize**.
2. Connect or authenticate the **synci** server when prompted.
3. Sign in to Synci, approve the read-only permission, and select the accounts Cursor may access.
4. Confirm that Synci's tools are available to the agent.

OAuth handles registration and sign-in. Do not add an API key, bearer token, or static client secret to this example. Keep Cursor's tool approval controls enabled as appropriate for your workflow.

## Try it

> Use Synci to summarize the last calendar month's transactions. Show the exact date range and separate totals by currency. Keep the result in this conversation.

Synci cannot edit financial data. Cursor may have other tools that can create local files, so be explicit if a financial summary should stay in chat. Revoke Synci access in Synci settings when needed.

See [more prompts](../../examples/prompts.md) and [troubleshooting](../troubleshooting.md).

## Sources

- [Synci product behavior and consent](https://docs.synci.io/mcp)
- [Cursor: Model Context Protocol](https://cursor.com/docs/mcp)

Documentation reviewed **2026-10-05**; not an authenticated Cursor connection test.

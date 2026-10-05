# Connect Synci to Claude

[← README](../../README.md) · [Synci MCP documentation](https://docs.synci.io/mcp)

Use Claude's remote custom-connector flow. An active Synci subscription and connected accounts are required. Workspace policy may require an owner or administrator to add the connector first.

## Add the connector

1. Open **Customize → Connectors** in Claude and choose **Add custom connector**. For an organization, use the corresponding controls in **Organization settings → Connectors**.
2. Name the connector **Synci** and enter this remote MCP server URL:

   ```text
   https://api.synci.io/mcp
   ```

3. Review the detected OAuth settings. If Claude offers an OAuth client choice, select **Register automatically**, matching Synci's documented dynamic client registration. Use the sign-in flow rather than fixed request headers.
4. Sign in to Synci, approve read-only financial access, and select the accounts Claude may see. No manual API key or client secret is required.
5. Enable Synci from the conversation's connectors menu and complete any pending sign-in prompt.

Remote connectors are managed through the Claude account and are separate from local server entries in `claude_desktop_config.json`. No local server process is supplied by this repository.

This guide uses the custom-connector path and does not depend on a Synci listing in Claude's directory. Consult Claude's current instructions if labels differ.

## Try it

> Use Synci to show my latest available balances. Group them by currency, include snapshot dates when available, and flag unhealthy connections.

The data comes from the latest provider sync. Synci cannot transfer funds, place trades, or modify your account. Revoke access from Synci settings when needed.

See [more prompts](../../examples/prompts.md) and [troubleshooting](../troubleshooting.md).

## Sources

- [Synci product behavior and consent](https://docs.synci.io/mcp)
- [Claude: Get started with custom connectors using remote MCP](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp)

Documentation reviewed **2026-10-05**; not an authenticated Claude connection test.

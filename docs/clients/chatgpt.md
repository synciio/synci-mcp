# Connect Synci to ChatGPT

[← README](../../README.md) · [Synci MCP documentation](https://docs.synci.io/mcp)

You need an active Synci subscription, connected accounts, and a ChatGPT account or workspace that permits the connection.

## Use the directory connection

Search ChatGPT's app/plugin directory for **Synci**. When the Synci listing is available to your account, open it and use its connect or sign-in action. Complete Synci's authorization flow, approve read-only access, and choose which accounts to share.

Enable Synci in your conversation's tools menu. Directory labels and availability may vary by account and workspace policy.

## Connect the endpoint manually

For accounts with developer mode, OpenAI's current instructions use **Settings → Security and login → Developer mode**, followed by **ChatGPT Plugins → plus button**.

1. Create a connection named **Synci**, described as read-only access to connected bank, brokerage, and crypto accounts.
2. Choose a public remote connection and enter:

   ```text
   https://api.synci.io/mcp
   ```

3. Use OAuth. If offered a client-registration choice, use **dynamic client registration (DCR)**, which Synci documents and advertises. You do not need to supply a client ID, client secret, or API key manually.
4. Complete the Synci sign-in and account-selection flow when prompted.
5. Review the discovered tools, then enable the connection in a new conversation.

If these controls are absent, check the current OpenAI instructions and your workspace administrator's policy.

## Try it

> Use Synci to list the accounts I authorized and check their connection health. Tell me if any data is missing or stale.

Synci returns data from the latest provider sync. It cannot change account data or move money. Revoke access in Synci settings when needed.

See [more prompts](../../examples/prompts.md) and [troubleshooting](../troubleshooting.md).

## Sources

- [Synci product behavior and consent](https://docs.synci.io/mcp)
- [OpenAI: Connect and test your plugin](https://developers.openai.com/plugins/deploy/connect-chatgpt)
- [OpenAI: Authentication](https://developers.openai.com/plugins/build/auth)

Documentation reviewed **2026-10-05**; not an authenticated ChatGPT connection test.

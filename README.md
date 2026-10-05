# Synci MCP

**Your connected finances, available to your AI assistant. Read-only.**

[Synci](https://synci.io) gives AI assistants read-only access to connected **bank, brokerage, and crypto accounts** through the Model Context Protocol (MCP). Ask about balances, transactions, holdings, and connection status/health using the financial data already connected to Synci.

[Product documentation](https://docs.synci.io/mcp) · [Client setup](#connect-your-assistant) · [Example prompts](examples/prompts.md) · [Security](SECURITY.md)

## Connect your assistant

Synci runs the server for you. Add this remote MCP endpoint to a compatible client:

```text
https://api.synci.io/mcp
```

| Setting | Value |
| --- | --- |
| Display name | Synci |
| Transport | Streamable HTTP |
| Authentication | OAuth with automatic client registration and PKCE |
| Permission | `mcp:use` — read-only financial data |
| Requirements | A Synci account, an active Synci subscription, and connected financial accounts |

1. Choose your client below and add Synci.
2. Sign in to Synci in the browser authorization flow.
3. Review the read-only permission and select the accounts your assistant may access.
4. Enable Synci in your conversation and ask: **“Which of my connected accounts are available, and are any connections unhealthy?”**

No manual API key or client secret is needed. You can revoke an assistant's access from your Synci settings.

| Client | Setup guide |
| --- | --- |
| ChatGPT | [Connect Synci to ChatGPT](docs/clients/chatgpt.md) |
| Claude | [Connect Synci to Claude](docs/clients/claude.md) |
| Cursor | [Connect Synci to Cursor](docs/clients/cursor.md) |
| Other MCP clients | [Remote MCP and OAuth requirements](docs/clients/generic.md) |

Client features and administrator policies can affect connection availability. The guides link to the clients' current documentation.

## What you can ask

- **Balances:** “Show my latest available balances, grouped by currency.”
- **Spending:** “Summarize last month's transactions by merchant and show the date range you used.”
- **Investments:** “List my brokerage and crypto holdings, including quantity and market value where available.”
- **Connection health:** “Which bank or provider connections need attention?”

See [example prompts](examples/prompts.md) for more precise requests and ways to handle missing or stale data.

## Available tools

| Tool | Purpose |
| --- | --- |
| `list_connections` | Inspect bank and provider connections and their health status. |
| `list_accounts` | Discover connected bank, brokerage/investment, and crypto accounts. |
| `get_account_balance` | Retrieve recent balance snapshots for an account. |
| `list_transactions` | Read transactions for a date range. |
| `list_holdings` | Read investment and crypto positions, including symbol, quantity, and market value. |

The assistant discovers the current tool inputs from the hosted server. See the [tool guide](docs/tools.md) and [authoritative Synci MCP documentation](https://docs.synci.io/mcp).

## Read-only, with account-level consent

Synci's MCP server cannot create, change, or delete anything in your Synci account. It cannot move money or place trades. You decide which accounts an assistant can see during authorization.

MCP responses omit sensitive identifiers such as IBANs, account numbers, card numbers, and owner names. Balances, transaction details, and holdings are still financial information; connect only assistants you trust to process that data.

**Data reflects the most recent sync from the relevant provider. It is not a real-time bank balance or market-price feed.** Availability depends on the accounts and data connected to Synci. Keep currencies and observation dates visible when comparing results.

Read [SECURITY.md](SECURITY.md) for the documented security model and private vulnerability reporting.

## About this repository

This is the official documentation and connection-example repository for **Synci's hosted MCP service**. It contains setup guides, example prompts, and public server metadata. The proprietary backend is not included, and this repository does not provide a server to install or self-host.

[server.json](server.json) mirrors the published MCP Registry descriptor for `io.synci/synci`. It describes a remote service, not an installable package. See [metadata notes](docs/metadata.md) for its provenance and maintenance guidance.

[docs.synci.io/mcp](https://docs.synci.io/mcp) is the authoritative source for product behavior. If these guides differ from the product docs, follow the product docs and [report the documentation issue](https://github.com/synciio/synci-mcp/issues/new/choose).

## Help and contributions

- Setup issues: start with [troubleshooting](docs/troubleshooting.md).
- Account or connection support: contact [support@synci.io](mailto:support@synci.io).
- Documentation fixes: see [CONTRIBUTING.md](CONTRIBUTING.md).
- Security reports: use the private contact in [SECURITY.md](SECURITY.md), not a public issue.

Product and client references checked on **2026-10-05**. This date records a documentation review, not an authenticated test of every client.

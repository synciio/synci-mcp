# Troubleshooting

[← README](../README.md) · [Synci MCP documentation](https://docs.synci.io/mcp)

## The client cannot connect

Confirm the remote URL is exactly:

```text
https://api.synci.io/mcp
```

Choose remote **Streamable HTTP** with OAuth. The documentation URL is a web page, not the MCP endpoint. Do not append a client name or replace the path with an assumed `/sse` endpoint.

Check that the client supports OAuth discovery, dynamic registration, and PKCE. Consult its current setup guide and any workspace restrictions. A client that only supports local commands cannot use this endpoint directly.

## I see “Unauthenticated” or HTTP 401

An unauthenticated request is expected to receive an authentication challenge. Seeing a 401 before sign-in does not mean the endpoint is broken. Connect through the client's OAuth flow, sign in to Synci, and finish consent.

If failures continue after sign-in, use the client's reconnect or sign-in action. Check that your Synci subscription is active. Do not work around the problem by pasting tokens into configuration files or public issues.

## The client requests a client ID or secret

Synci documents automatic client registration and public-client PKCE. Check whether the client is configured for dynamic registration rather than a static OAuth client. In Claude, this may be labeled **Register automatically**. Client ID Metadata Documents (CIMD) are a separate mechanism; use Synci's documented DCR route if the client asks you to choose.

If the client cannot perform that flow, consult its official documentation or use a compatible client.

## Accounts are missing

Check that the accounts are connected in Synci and were selected during authorization. If you need a different account selection, reconnect and review the consent screen. Use `list_accounts` to inspect what is available and `list_connections` to check provider health.

Do not share real account details in a public GitHub issue. Account-specific questions belong with [Synci support](mailto:support@synci.io).

## Balances, transactions, or holdings look stale or incomplete

Synci's MCP data comes from the most recent provider sync. Check connection health and the information shown in Synci. For transactions, confirm the requested date range. For all results, check the selected account, currency, and available timestamps.

Missing data should be reported as unavailable, not interpreted as zero. An assistant cannot force a provider refresh through the five documented read-only tools.

## The assistant tries to change financial data

Synci's MCP tools cannot create, modify, or delete Synci data, move funds, or place trades. Ask the assistant to inspect or summarize the available data instead. Other tools connected to the same assistant may have separate capabilities.

## I want to disconnect

Revoke the assistant's connection in **Synci settings**. You can also remove the connector from the client. Deleting a local configuration file alone does not establish that server-side authorization has been revoked.

## Still need help?

For documentation mistakes, [open a documentation issue](https://github.com/synciio/synci-mcp/issues/new/choose) with the affected page, client/version, and a redacted description. For account support or security concerns, email [support@synci.io](mailto:support@synci.io); see [SECURITY.md](../SECURITY.md).

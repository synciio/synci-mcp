# Connect any compatible MCP client

[← README](../../README.md) · [Synci MCP documentation](https://docs.synci.io/mcp)

Synci provides a hosted MCP endpoint. There is nothing to clone or start locally to use the service.

## Required client capabilities

Your client must support remote MCP over **Streamable HTTP** and Synci's browser-based OAuth flow, including discovery, dynamic client registration, and PKCE with `S256`.

| Field | Value |
| --- | --- |
| Name | Synci |
| Remote URL | `https://api.synci.io/mcp` |
| Authentication | OAuth |
| Client registration | Automatic / dynamic |
| Scope | `mcp:use` |

Configuration keys differ by client. Use its remote-server settings; do not assume the [Cursor JSON example](../../examples/cursor-mcp.json) is a universal configuration format. Clients supporting only local `stdio` servers need additional remote/OAuth support that this repository does not provide.

## Connect and verify

1. Add a remote server with the settings above.
2. Let the client discover the authorization configuration and register itself.
3. Sign in to Synci in the browser, review the read-only permission, and select the accounts to share. An active Synci subscription is required.
4. Return to the client and let it initialize the MCP connection and discover tools.
5. Ask the assistant to list the available accounts and connection health before requesting balances, transactions, or holdings.

No manual API key, developer credential, or client secret is needed. Do not paste bank credentials or OAuth tokens into chat.

## For client implementers

Use MCP discovery rather than hard-coding authorization and token endpoints. Synci's unauthenticated MCP response advertises a protected-resource metadata URL in its `WWW-Authenticate` header. The resource metadata identifies the authorization server and `mcp:use` scope. Authorization-server metadata advertises the registration endpoint, authorization-code flow, and `S256` PKCE support.

Use the live `tools/list` response for tool names, input schemas, and descriptions. Do not derive MCP arguments from Synci's separate REST API or assume undocumented parameters. The [tool guide](../tools.md) describes intended uses without freezing those schemas.

Use a client that manages OAuth credentials securely. Revoke the assistant's access from Synci settings when needed.

## Expected first result

> List the accounts I authorized through Synci and the health of their provider connections. If there are no accounts, explain that instead of inventing financial data.

Account visibility depends on consent. Data reflects the latest provider sync and the tools remain read-only.

Sources: [Synci MCP documentation](https://docs.synci.io/mcp), [published server metadata](../metadata.md), and Synci's public OAuth discovery responses. Checked **2026-10-05**. The unauthenticated endpoint and discovery were checked; no financial accounts were accessed.

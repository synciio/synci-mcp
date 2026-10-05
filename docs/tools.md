# Tool guide

[← README](../README.md) · [Synci MCP documentation](https://docs.synci.io/mcp)

These are the five read-only tools listed in Synci's product documentation. The hosted server supplies current input schemas through MCP discovery; this repository intentionally does not invent JSON arguments or sample financial responses.

| Tool | Data available | Useful request |
| --- | --- | --- |
| `list_connections` | Bank and provider connections, including health status | “Which of my connections need attention?” |
| `list_accounts` | Connected bank, brokerage/investment, and crypto accounts | “Which accounts can you access through Synci?” |
| `get_account_balance` | Recent balance snapshots for one account | “Show the latest available balance for this account.” |
| `list_transactions` | Transactions within a date range | “Summarize last month's transactions for this account.” |
| `list_holdings` | Investment and crypto positions, including symbol, quantity, and market value | “List the holdings in my authorized brokerage and crypto accounts.” |

## A useful sequence

Start by discovering accounts and checking connection health. Use those results to identify the account for a balance, transaction, or holdings request. If a name is ambiguous, have the assistant ask you to choose an account.

For transaction analysis, specify the date range and ask the assistant to state it in the response. For balances and holdings, ask for available observation dates and currencies. Let the client follow the live tool schema for required inputs and any pagination or result limits it exposes.

## Interpret results carefully

- **Sync timing:** values reflect the most recent bank or provider sync, not real-time data.
- **Consent:** an account outside the authorization grant is not available to the assistant.
- **Missing data:** an empty or unavailable result is not proof of a zero balance or no activity.
- **Currencies:** separate totals by currency unless an explicit exchange-rate source and date are provided.
- **Coverage:** analysis covers the data available through the connected, authorized accounts, not necessarily your entire financial position.

The assistant can summarize or calculate from returned data. That does not add a write capability to Synci. There are no MCP tools here for payments, trades, editing transactions, or deleting accounts.

See [example prompts](../examples/prompts.md) and [troubleshooting](troubleshooting.md).

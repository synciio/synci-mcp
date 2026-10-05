# Example prompts

[← README](../README.md) · [Available tools](../docs/tools.md) · [Synci MCP documentation](https://docs.synci.io/mcp)

Use these after connecting Synci and selecting the accounts your assistant may access. They are suggested questions, not guarantees that every account or provider supplies every data type.

## Check coverage first

> Use Synci to list the financial accounts I authorized and check the health of their provider connections. Flag any unavailable data before doing further analysis.

## Review balances

> Show the latest available balance for each authorized account. Group by currency, include snapshot dates when available, and avoid combining different currencies into one total.

## Understand spending

> Summarize my transactions for the last calendar month. State the exact date range, show the largest merchants and recurring-looking charges, and separate totals by currency. Explain any assumptions or incomplete results.

## Compare two periods

> Compare transactions for the last two complete calendar months using the same authorized accounts. Separate income and spending where the data supports it, identify possible transfers without assuming they are expenses, and explain gaps in coverage.

## Review brokerage and crypto holdings

> List my available brokerage and crypto holdings by account, with symbols, quantities, and market values where supplied. Show valuation currencies and available dates. Flag missing values instead of filling them in.

## Find connections needing attention

> Check my Synci connection health. Tell me which connections report a problem and what the returned status says. If I need to act, point me back to Synci rather than claiming to fix the connection.

## Keep a summary private to the conversation

> Create a concise financial snapshot from my authorized Synci accounts. Note currencies, data dates, and coverage limits. Keep it in this conversation and do not create files or send it anywhere.

## Useful follow-ups

- “Which tool results support that conclusion?”
- “Which accounts and dates were included?”
- “What data was missing?”
- “Was that category supplied by Synci or inferred by you?”

Synci's MCP access is read-only, and returned data reflects the latest provider sync. These prompts do not authorize payments, trades, changes to financial records, or sharing through another tool.

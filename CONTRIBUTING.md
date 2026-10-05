# Contributing

Contributions to setup guides, example prompts, accessibility, and documentation accuracy are welcome. This repository documents Synci's hosted MCP service; backend implementation changes belong outside this repository.

## Before opening an issue

Check the [Synci MCP documentation](https://docs.synci.io/mcp) and [troubleshooting guide](docs/troubleshooting.md). Product behavior in the official documentation takes precedence over examples here.

Use GitHub issues for public documentation feedback. Send account-specific support requests to [support@synci.io](mailto:support@synci.io). Follow [SECURITY.md](SECURITY.md) for vulnerabilities.

## Make a documentation change

1. Fork the repository and create a branch for your change.
2. Keep the change focused and link to the authoritative source for any changed behavior.
3. For client setup changes, cite that client's official documentation and record the review date. Distinguish a documentation review from an actual connection test.
4. Open a pull request explaining the problem, the change, and what you checked.

Use **Synci** as the product name and describe its MCP access as read-only access to connected bank, brokerage, and crypto accounts. Use `https://api.synci.io/mcp` consistently unless the authoritative Synci documentation changes.

## Review checklist

- Relative links and code blocks work on GitHub.
- JSON examples parse and contain no credentials or private data.
- Tool names match the product documentation. Do not invent tool arguments; clients discover current schemas from the server.
- Examples do not imply real-time data, write access, money movement, trading, or an open-source backend.
- Setup instructions retain OAuth and account selection rather than introducing manual API keys.
- [server.json](server.json) remains consistent with the published record and its referenced schema; see [metadata notes](docs/metadata.md).

Use invented scenarios for examples. Never submit production responses, real transactions, account details, tokens, environment files, or proprietary backend code.

There is no application build or local server to run in this repository. Documentation contributions do not require connecting a financial account.

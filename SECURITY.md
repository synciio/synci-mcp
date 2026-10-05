# Security

## Report a vulnerability privately

Email **[support@synci.io](mailto:support@synci.io)** if you believe you have found a security issue in Synci's MCP service or these connection examples. This is the reporting address published in the [Synci MCP documentation](https://docs.synci.io/mcp).

Do not open a public issue or pull request containing vulnerability details, access tokens, authorization codes, credentials, or customer financial data.

Include a concise description, the affected component, expected versus observed behavior, and minimal reproduction steps using accounts you control. Redact private data and secrets from any supporting material. Synci's documentation states that it does not operate a paid bug bounty program.

## Scope of this repository

This repository contains documentation, public metadata, and connection examples for a hosted service. It does not contain the proprietary MCP backend or a self-hostable distribution. Documentation versions do not identify deployed backend versions.

Use the same private contact for suspected service vulnerabilities and documentation mistakes that could expose credentials or private information.

## Documented service controls

The [product documentation](https://docs.synci.io/mcp) describes these controls:

- **Read-only tools:** MCP access cannot create, modify, or delete Synci data.
- **Restricted scope:** automatically registered clients are confined to `mcp:use`; this does not grant REST API, Developer Program, or write access.
- **Explicit consent:** users sign in, review the requesting client, and select the accounts it may access. An active Synci subscription is required.
- **PKCE:** public clients must use the `S256` challenge method. Their OAuth flow does not require a client secret.
- **Redirect validation:** authorization uses an exact registered redirect URI. Registration permits HTTPS and HTTP localhost loopback callbacks; unsafe browser schemes are rejected.
- **Revocation:** users can disconnect assistants in Synci settings.
- **Limited token lifetimes:** the docs specify one hour for access tokens and 30 days for refresh tokens.
- **Identifier omission:** MCP responses exclude IBANs, account numbers, card numbers, and owner names.

Dynamic client registration is intentionally public. The existence of the registration endpoint alone is not a vulnerability; a report should describe a bypass or unintended exposure.

These statements summarize Synci's published controls. They are not an independent security audit or a guarantee about an AI client's storage and processing of returned data.

## Safe use and sharing

Authorize only the accounts needed for the task. Complete sign-in on Synci's authorization page rather than pasting credentials into an assistant conversation or configuration file. Review your AI client's data controls before connecting.

Keep tokens, browser callback URLs containing codes, account identifiers, and real financial records out of issues, screenshots, configuration examples, and commits. If access should end, revoke it in Synci settings; removing a local example file is not a substitute for revocation.

Source reviewed: **2026-10-05**. Consult the product documentation for current controls.

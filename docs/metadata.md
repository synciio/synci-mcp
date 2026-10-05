# Server metadata

[← README](../README.md) · [Synci MCP documentation](https://docs.synci.io/mcp)

## Existing registry identity

Synci is published in the official MCP Registry as **`io.synci/synci`**, version **`1.0.0`**. The record was active and marked latest when checked on **2026-10-05**.

[server.json](../server.json) is a verbatim JSON-data copy of the `server` object returned by the [official registry lookup](https://registry.modelcontextprotocol.io/v0.1/servers?search=synci), formatted for readability. Registry-owned status and timestamps are not included in the descriptor.

The existing descriptor uses the word “investment” for accounts described as “brokerage” in this repository's positioning. It points to the same hosted service:

```text
https://api.synci.io/mcp
```

The descriptor declares **Streamable HTTP** and references the [2025-12-11 server schema](https://static.modelcontextprotocol.io/schemas/2025-12-11/server.schema.json). Its version is the published descriptor's version; it is not a release of backend source code in this repository.

## Why there is no source package or repository field

Synci hosts the service. There is no npm, Python, container, or other installable server package in this repository. The registry schema describes its `repository` field as a link to the server's source code, so the published descriptor omits that field. A documentation repository should not be represented as inspectable backend source.

Use this repository's GitHub URL when a directory requests documentation or a project reference, and identify it as documentation. Use [docs.synci.io/mcp](https://docs.synci.io/mcp) for authoritative product behavior and setup requirements.

## Maintaining the descriptor

Before changing `server.json`, compare it with the latest `io.synci/synci` record and validate it against its referenced JSON Schema. Coordinate descriptor changes with Synci's existing registry publishing process. Do not create a second registry identity merely because this repository is named `synci-mcp`.

Committing this file does not publish or update the MCP Registry. This repository includes no registry-publishing workflow or credentials.

See the registry's [server.json format specification](https://github.com/modelcontextprotocol/registry/blob/main/docs/reference/server-json/generic-server-json.md) for the supported fields.

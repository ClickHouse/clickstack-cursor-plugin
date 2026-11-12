# ClickStack Cursor plugin

Cursor plugin that connects Cursor's agent to **ClickStack** via **MCP**.

## What’s included

- **MCP** – ClickStack MCP server config in `mcp.json`.

## How to use

After the plugin is installed from the **Cursor Marketplace**, the ClickStack MCP is available to Cursor’s agent.

Once you’ve authenticated, Cursor can use it to investigate incidents and explore your observability data, for example:

- *“Which services have the highest error rate in the last hour?”*
- *“Show me the slowest traces for the checkout service today.”*
- *“What new log patterns appeared since the last deploy?”*
- *“Create a dashboard with p95 latency and error rate per service.”*

The MCP can query logs, traces, and metrics; manage dashboards, alerts, and saved searches; and explore data sources. See the [ClickStack MCP server docs](https://clickhouse.com/docs/use-cases/observability/clickstack/mcp) for details.

## Install

Install the **ClickStack** plugin from the **Cursor Marketplace**.
Once installed, follow the prompt to authenticate with your ClickHouse Cloud account using OAuth.

## Self-hosted ClickStack

This plugin targets Managed ClickStack in ClickHouse Cloud. For Open Source or BYOC ClickStack, configure the MCP server manually with your instance URL and a Personal API Access Key, as described in the [ClickStack MCP server docs](https://clickhouse.com/docs/use-cases/observability/clickstack/mcp#cursor).

## Related

- [ClickHouse Cursor plugin](https://github.com/ClickHouse/clickhouse-cursor-plugin) – ClickHouse best-practice skills and the ClickHouse MCP.

## License

Apache 2.0. See [LICENSE](LICENSE).

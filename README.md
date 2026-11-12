# ClickStack Cursor plugin

Cursor plugin that connects agents to [Managed ClickStack](https://clickhouse.com/clickstack), the observability stack built on ClickHouse Cloud, through ClickStack's remote [Model Context Protocol](https://modelcontextprotocol.io/) server.

Investigate logs, metrics, and traces, and build dashboards, alerts, and saved searches from chat.

## Install

1. Open **Cursor Settings → Plugins**.
2. Search for **ClickStack**.
3. Click **Install**, then sign in with your ClickHouse Cloud account when prompted.

## MCP

```json
{
  "mcpServers": {
    "clickstack": {
      "type": "http",
      "url": "https://mcp.clickhouse.cloud/clickstack"
    }
  }
}
```

Auth is OAuth. ClickStack uses the authorization code flow with PKCE (S256) and dynamic client registration, so there is no API key or client ID to configure. Cursor prompts for ClickHouse Cloud sign-in when the plugin connects. Each user signs in with their own account, and tool calls only reach the teams, sources, and data that account can already access.

## Before you connect

You need:

- A ClickHouse Cloud account with access to a service that has Managed ClickStack enabled.
- MCP access turned on for that service (**Connect → Connect with MCP** in the ClickHouse Cloud console).
- Logs, metrics, or traces ingested into ClickStack.

## What agents can do

| Category | Capabilities |
| --- | --- |
| Discovery | List data sources and inspect their schemas, attributes, and metrics |
| Service health | Throughput, error rate, and p50/p95/p99 latency per service, compared with the previous day |
| Search and analytics | Search and aggregate logs, traces, and metrics, and plot trends over time |
| Investigation | Find recurring log patterns, new or disappearing signals, and attributes that distinguish slow or failing requests |
| Traces | Open a single trace as a span waterfall and find its slowest operations |
| Sharing | Create and update dashboards, alerts, and saved searches so findings can be shared with your team |

The hosted server is the source of truth for tool names and schemas. See the [ClickStack MCP docs](https://clickhouse.com/docs/clickstack/mcp) for details.

Example prompts:

- *"Show me the services with the highest error rate over the last 24 hours."*
- *"What are the most common error log patterns in the last hour?"*
- *"Explore my ClickStack data sources and summarize what data is available."*

## Notes

- Some tools write to ClickStack: dashboards, alerts, saved searches, sources, and webhooks, including deletes. Confirm the team and the change before letting the agent write.
- The plugin does not ingest telemetry, change ClickHouse Cloud service configuration or billing, or access data outside your ClickStack teams.
- This plugin targets Managed ClickStack in ClickHouse Cloud. For Open Source or BYOC ClickStack, configure the MCP server manually with your instance URL and a Personal API Access Key, as described in the [ClickStack MCP docs](https://clickhouse.com/docs/clickstack/mcp).

## Related

- [ClickHouse Cursor plugin](https://github.com/ClickHouse/clickhouse-cursor-plugin): ClickHouse best-practice skills and the ClickHouse MCP.

## Links

- Website: https://clickhouse.com/clickstack
- Docs: https://clickhouse.com/docs/clickstack/mcp
- Support: https://clickhouse.com/support/program
- Privacy policy: https://clickhouse.com/legal/privacy-policy
- Terms: https://clickhouse.com/legal/clickhouse-general-terms-and-conditions

## License

Apache 2.0. See [LICENSE](LICENSE).

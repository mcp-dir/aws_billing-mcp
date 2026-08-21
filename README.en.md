# AWS Billing

### AWS Billing for Claude, ChatGPT and AI agents

AWS Cost Explorer cost, forecast, and anomaly reporting through user-connected IAM credentials.

- 📊 **4 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `AWS Billing`, URL `https://api.mcp.ai/p_aws_billing`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=aws_billing&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9hd3NfYmlsbGluZyJ9)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=aws_billing&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_aws_billing%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_aws_billing
```

---

## 4 tools

| Tool | Description |
|---|---|
| `aws_billing_list_accounts` | List AWS Billing credential records linked to this install. |
| `aws_billing_cost` | Get normalized AWS Cost Explorer cost and usage with daily breakdown and top services. |
| `aws_billing_forecast` | Get normalized AWS Cost Explorer forecast for the next 30 days or an explicit date range. |
| `aws_billing_anomalies` | Get normalized AWS Cost Anomaly Detection anomalies for a date range. |

---

## Pricing

Free.

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_aws_billing` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.

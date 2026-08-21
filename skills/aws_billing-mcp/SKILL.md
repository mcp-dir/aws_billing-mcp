---
name: aws_billing-mcp
description: Skill da REST API do AWS Billing na MCP.AI: 4 endpoints em /api/aws_billing. AWS Cost Explorer cost, forecast, and anomaly reporting through user-connected IAM credentials. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# AWS Billing — REST API skill

Você tem acesso à **AWS Billing** REST API na MCP.AI.

> AWS Cost Explorer cost, forecast, and anomaly reporting through user-connected IAM credentials.

## Base URL

```
https://api.mcp.ai/api/aws_billing
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/aws_billing/anomalies \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/aws_billing/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (4)

#### `aws_billing_anomalies`

Get normalized AWS Cost Anomaly Detection anomalies for a date range. _(POST /api/aws_billing/anomalies)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `days_back` | integer | Não | Relative range in days. |
| `start_date` | string | Não | Start date YYYY-MM-DD. |
| `end_date` | string | Não | End date YYYY-MM-DD. |
| `limit` | integer | Não | Per-page anomaly limit; pagination is drained inside the adapter. |
| `account` | string | Não | When multiple AWS credential records are connected: connection id or label. See aws_billing_list_accounts. |

#### `aws_billing_cost`

Get normalized AWS Cost Explorer cost and usage with daily breakdown and top services. _(POST /api/aws_billing/cost)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `days_back` | integer | Não | Relative range in days. |
| `start_date` | string | Não | Start date YYYY-MM-DD. |
| `end_date` | string | Não | End date YYYY-MM-DD. |
| `granularity` | string | Não |  (DAILY, MONTHLY, HOURLY) |
| `group_by` | string | Não | Cost Explorer dimension key, default SERVICE. |
| `account` | string | Não | When multiple AWS credential records are connected: connection id or label. See aws_billing_list_accounts. |

#### `aws_billing_forecast`

Get normalized AWS Cost Explorer forecast for the next 30 days or an explicit date range. _(POST /api/aws_billing/forecast)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `start_date` | string | Não | Start date YYYY-MM-DD. |
| `end_date` | string | Não | End date YYYY-MM-DD. |
| `granularity` | string | Não |  (DAILY, MONTHLY) |
| `metric` | string | Não |  (BLENDED_COST, UNBLENDED_COST, AMORTIZED_COST, NET_UNBLENDED_COST, NET_AMORTIZED_COST, USAGE_QUANTITY, NORMALIZED_USAGE_AMOUNT) |
| `account` | string | Não | When multiple AWS credential records are connected: connection id or label. See aws_billing_list_accounts. |

#### `aws_billing_list_accounts`

List AWS Billing credential records linked to this install. _(POST /api/aws_billing/list/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | When multiple AWS credential records are connected: connection id or label. See aws_billing_list_accounts. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_aws_billing` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).

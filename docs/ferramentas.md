# Ferramentas

AWS Billing expõe 4 ferramentas (todas somente leitura).

### 1. `aws_billing_list_accounts`
**Input**: `account` (opcional)

List AWS Billing credential records linked to this install.

### 2. `aws_billing_cost`
**Input**: `days_back` (opcional), `start_date` (opcional), `end_date` (opcional), `granularity` (opcional), `group_by` (opcional), `account` (opcional)

Get normalized AWS Cost Explorer cost and usage with daily breakdown and top services.

### 3. `aws_billing_forecast`
**Input**: `start_date` (opcional), `end_date` (opcional), `granularity` (opcional), `metric` (opcional), `account` (opcional)

Get normalized AWS Cost Explorer forecast for the next 30 days or an explicit date range.

### 4. `aws_billing_anomalies`
**Input**: `days_back` (opcional), `start_date` (opcional), `end_date` (opcional), `limit` (opcional), `account` (opcional)

Get normalized AWS Cost Anomaly Detection anomalies for a date range.

## Prompts de exemplo

```
Show AWS cost by service for the last 30 days
Forecast AWS spend for the next month
List recent AWS cost anomalies
```

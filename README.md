# AWS Billing

### AWS Billing para Claude, ChatGPT e agentes de IA

AWS Cost Explorer cost, forecast, and anomaly reporting through user-connected IAM credentials.

- 📊 **4 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `AWS Billing` e **URL** `https://api.mcp.ai/p_aws_billing`.

### Cursor

[➕ Instalar AWS Billing no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=aws_billing&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9hd3NfYmlsbGluZyJ9)

### VS Code (Copilot Chat)

[➕ Instalar AWS Billing no VS Code](vscode:mcp/install?name=aws_billing&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_aws_billing%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_aws_billing
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Show AWS cost by service for the last 30 days
Forecast AWS spend for the next month
List recent AWS cost anomalies
```

---

## 4 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `aws_billing_list_accounts` | List AWS Billing credential records linked to this install. |
| `aws_billing_cost` | Get normalized AWS Cost Explorer cost and usage with daily breakdown and top services. |
| `aws_billing_forecast` | Get normalized AWS Cost Explorer forecast for the next 30 days or an explicit date range. |
| `aws_billing_anomalies` | Get normalized AWS Cost Anomaly Detection anomalies for a date range. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Grátis.

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_aws_billing`.


---

## Suporte

- 📧 [aws_billing@mcp.ai](mailto:aws_billing@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/aws_billing-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_aws_billing` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.

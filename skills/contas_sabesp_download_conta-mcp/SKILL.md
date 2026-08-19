---
name: contas_sabesp_download_conta-mcp
description: Skill da REST API do SABESP: Download de Conta na MCP.AI: 1 endpoint em /api/contas_sabesp_download_conta. SABESP: Download de Conta, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# SABESP: Download de Conta — REST API skill

Você tem acesso à **SABESP: Download de Conta** REST API na MCP.AI.

> SABESP: Download de Conta, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/contas_sabesp_download_conta
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
curl -X POST https://api.mcp.ai/api/contas_sabesp_download_conta/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"login_cpf":"...","login_senha":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/contas_sabesp_download_conta/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `contas_sabesp_download_conta_consultar`

SABESP: Download de Conta, consulta em fonte oficial. _(POST /api/contas_sabesp_download_conta/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `login_cpf` | string | Sim | Parâmetro de consulta "login_cpf". |
| `login_senha` | string | Sim | Parâmetro de consulta "login_senha". |
| `cnpj` | string | Não | Parâmetro de consulta "cnpj". |
| `fornecimento` | string | Não | Parâmetro de consulta "fornecimento". |
| `ano_mes` | string | Não | Parâmetro de consulta "ano_mes". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_contas_sabesp_download_conta` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).

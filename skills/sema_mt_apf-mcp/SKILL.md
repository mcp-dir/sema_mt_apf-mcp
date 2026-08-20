---
name: sema_mt_apf-mcp
description: Skill da REST API do SEMA MT: APF Rural na MCP.AI: 1 endpoint em /api/sema_mt_apf. SEMA MT: APF Rural, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# SEMA MT: APF Rural — REST API skill

Você tem acesso à **SEMA MT: APF Rural** REST API na MCP.AI.

> SEMA MT: APF Rural, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/sema_mt_apf
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
curl -X POST https://api.mcp.ai/api/sema_mt_apf/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/sema_mt_apf/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `sema_mt_apf_consultar`

SEMA MT: APF Rural, consulta em fonte oficial. _(POST /api/sema_mt_apf/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cpf_proprietario` | string | Não | Parâmetro de consulta "cpf_proprietario". |
| `cnpj_proprietario` | string | Não | Parâmetro de consulta "cnpj_proprietario". |
| `cpf_responsavel` | string | Não | Parâmetro de consulta "cpf_responsavel". |
| `apf` | string | Não | Parâmetro de consulta "apf". |
| `car` | string | Não | Parâmetro de consulta "car". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_sema_mt_apf` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).

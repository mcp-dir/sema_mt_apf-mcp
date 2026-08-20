# Instalação rápida

SEMA MT: APF Rural é um servidor MCP remoto hospedado em `https://api.mcp.ai/p_sema_mt_apf`. Você não baixa nem roda nada localmente — só aponta seu cliente pra essa URL.

A auth acontece em runtime: clientes com **OAuth 2.1** (Claude Desktop, Cursor, VS Code recentes) abrem o browser na 1ª chamada (magic-link). Clientes sem OAuth recebem a tool `authenticate` — abra `https://app.mcp.ai/agent-auth`, faça login, copie o JWT e cole no chat.

---

## Claude (Web e Desktop)

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → `SEMA MT: APF Rural` / `https://api.mcp.ai/p_sema_mt_apf`.

Config file (legado): `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS) ou `%APPDATA%\Claude\claude_desktop_config.json` (Windows):

```json
{ "mcpServers": { "sema_mt_apf": { "type": "http", "url": "https://api.mcp.ai/p_sema_mt_apf" } } }
```

## Cursor

[➕ Instalar no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=sema_mt_apf&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9zZW1hX210X2FwZiJ9)

`.cursor/mcp.json`:
```json
{ "mcpServers": { "sema_mt_apf": { "url": "https://api.mcp.ai/p_sema_mt_apf" } } }
```

## VS Code (Copilot Chat)

[➕ Instalar no VS Code](vscode:mcp/install?name=sema_mt_apf&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_sema_mt_apf%22%7D)

`.vscode/mcp.json`:
```json
{ "servers": { "sema_mt_apf": { "type": "http", "url": "https://api.mcp.ai/p_sema_mt_apf" } } }
```

## Outros clientes MCP

Qualquer cliente com **MCP over HTTP**. URL fixa:

```
https://api.mcp.ai/p_sema_mt_apf
```

Dúvidas? [sema_mt_apf@mcp.ai](mailto:sema_mt_apf@mcp.ai)

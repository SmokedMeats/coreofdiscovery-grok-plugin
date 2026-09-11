---
name: connect
description: Connect CoreOfDiscovery when MCP is unauthorized or the user has no API key.
when-to-use: Unauthorized MCP, missing COREOFDISCOVERY_API_KEY, install help, or first-run connect.
---

# Connect

The server URL is already in this plugin. Do not ask the user to find or type it.

`https://coreofdiscovery.vercel.app/api/mcp`

## Steps

1. Tell them to sign in and open [Settings → API keys](https://coreofdiscovery.vercel.app/settings/api-keys).
2. Create a key named for this agent. Check `mcp:tools`, `decisions:write`, and `calibration:read`.
3. They copy the `cod_...` secret once.
4. They set header `x-api-key` (Grok Build: `COREOFDISCOVERY_API_KEY`). Done when `tools/list` returns.
5. Do not invent a key. Do not reuse another person's key.

If they are on grok.com/connectors Custom, the form still asks for a URL. Paste the URL above and the same header.

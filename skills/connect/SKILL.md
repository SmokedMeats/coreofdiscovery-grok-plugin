---
name: connect
description: Connect CoreOfDiscovery when MCP is unauthorized or the user has no session.
when-to-use: Unauthorized MCP, Connect / OAuth prompt, missing key, install help, or first-run connect.
---

# Connect

The server URL is already in this plugin. Do not ask the user to find or type it.

`https://coreofdiscovery.vercel.app/api/mcp`

## Preferred

1. Call any MCP tool. If Grok opens a browser, they sign in to CoreOfDiscovery and Allow.
2. Done when `tools/list` returns. Do not invent a key.

## Fallback

If OAuth does not start (Custom connector that only accepts a header):

1. They sign in and open [Settings → API keys](https://coreofdiscovery.vercel.app/settings/api-keys).
2. Create a key with `mcp:tools`, `decisions:write`, and `calibration:read`.
3. Set header `x-api-key` (Grok Build: `COREOFDISCOVERY_API_KEY`).
4. Do not reuse another person's key.

On grok.com/connectors Custom, paste the URL above. Prefer Connect / OAuth when the client offers it.

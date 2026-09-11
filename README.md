# CoreOfDiscovery Grok plugin

Installable Grok plugin for [CoreOfDiscovery](https://github.com/SmokedMeats/CoreofDiscovery). Works with Grok Build, Grok Bot, and [Grok chat connectors](https://grok.com/connectors).

This repository is the plugin mouth: skills, commands, MCP client config, and a static install page. It has no database. Claims, grades, and lessons stay on the CoreOfDiscovery MCP server.

**MCP server:** `https://coreofdiscovery.vercel.app/api/mcp`  
**Install page:** [coreofdiscovery-grok-plugin.vercel.app](https://coreofdiscovery-grok-plugin.vercel.app)

## What you provide

Your own CoreOfDiscovery API key. The plugin already knows the server URL.

1. Sign in at [coreofdiscovery.vercel.app](https://coreofdiscovery.vercel.app).
2. Open [Settings → API keys](https://coreofdiscovery.vercel.app/settings/api-keys).
3. Create a key with `mcp:tools`, `decisions:write`, and `calibration:read`.
4. Copy the `cod_...` secret once.

Do not put a key in git. Do not share one key across people.

## Grok Build

```sh
grok plugin install coreofdiscovery --trust
```

Or clone this repo and install the folder. Set one environment variable:

```sh
export COREOFDISCOVERY_API_KEY=cod_...
```

The bundled `.mcp.json` already points at production. Reload plugins, then `/log-claim`.

```sh
grok plugin details coreofdiscovery
```

## Grok Bot

Settings → Plugins → add a custom MCP server (or ask the Bot to add one).

- URL: `https://coreofdiscovery.vercel.app/api/mcp`
- Header: `x-api-key` = your key

In chat, type `@` and attach the connector.

## Grok chat connectors

[grok.com/connectors](https://grok.com/connectors) → New → Custom → same URL and `x-api-key`. xAI’s form still asks for the URL; paste the production address above.

## Network and credentials

| Endpoint | Why |
| --- | --- |
| `https://coreofdiscovery.vercel.app/api/mcp` | JSON-RPC tools (`log_claim`, `recall_lessons`, `record_lesson`, `resolve_decision`, `calibration_report`, `list_open_claims`) |
| `https://coreofdiscovery.vercel.app/settings/api-keys` | Human creates their key |

Header `x-api-key` is the caller’s CoreOfDiscovery secret. This plugin never ships a shared key.

## Skills and commands

| Skill / command | When |
| --- | --- |
| `connect` / `/connect` | First run, or MCP unauthorized |
| `log-claim` / `/log-claim` | Before a date, probability, or recommendation you cannot look up now |
| `learn-from-outcomes` | Recall before log; record after grade |
| `self-grade` / `/grade-claim` | Grade the frozen ask |
| `report-to-user` / `/how-did-i-do` | Speak calibration |

Rules: quote the original request. Self-grade is down-weighted. Do not write lessons into a user’s `AGENTS.md`.

## License

MIT. See [LICENSE](LICENSE).

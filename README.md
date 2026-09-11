# CoreOfDiscovery Grok plugin

Grok Bot (and Grok Build / Grok chat) mouth for [CoreOfDiscovery](https://github.com/SmokedMeats/CoreofDiscovery).

Bots dump claims they or their user think matter. Later they grade **the frozen original ask** against what happened. Then they report calibration to the user.

This repo is skills, commands, MCP client config, and a static install page. It has **no database**. Decision math, snapshots, and Brier scores stay on CoreOfDiscovery MCP.

## Install

See the [install page](./index.html) after deploy, or:

1. Mint a CoreOfDiscovery API key.
2. Set `COREOFDISCOVERY_MCP_URL` and `COREOFDISCOVERY_API_KEY`.
3. Grok Bot: Settings → Plugins → custom MCP → `{APP}/api/mcp` with `x-api-key`.
4. Grok chat: [connectors](https://grok.com/connectors) → Custom.
5. Grok Build: install this folder as a plugin.

## Rules the skills enforce

- Quote the original request. Do not overwrite it on grade.
- `graderKind=self` never gets full calibration weight.
- The user report is ask / I said / happened / who graded.

## Tracker

- Map: [#1](https://github.com/SmokedMeats/coreofdiscovery-grok-plugin/issues/1)
- Kanban: [Bot claim calibration](https://github.com/users/SmokedMeats/projects/5)

# convex-kimi-plugin

The official [Convex](https://www.convex.dev) plugin for the [Kimi Code CLI](https://github.com/moonshotai/kimi-code).

Adds a reactive, type-safe backend to JS/TS apps: scaffold a running Next.js +
Convex app from one sentence (`$quickstart`), add capabilities from the Convex
component ecosystem (`$add`), plus auth, billing, crons, domains, migrations,
seeding, testing, a `convex-expert`, a `convex-reviewer`, and live
error-watching via MCP.

## Install

```
/plugins install https://github.com/get-convex/convex-kimi-plugin
```

## Layout

- `plugins/marketplace.json` — plugin registry for this repo (generated).
- `plugins/official/convex/kimi.plugin.json` — the plugin manifest (generated).
- `plugins/official/convex/skills/<id>/SKILL.md` — one skill per capability (generated).
- `plugins/official/convex/mcp/` — the `convex-plugin` MCP server (live error-watching).

## Generated — do not hand-edit

The skills and manifests here are **generated** from the
[convex-agents](https://github.com/get-convex/convex-agents) hub
(`content/capabilities/*.json` → `generators/forge.mjs` + `generators/kimi.mjs`).
Fix knowledge there, regenerate, and PR the result here.

## License

Apache-2.0

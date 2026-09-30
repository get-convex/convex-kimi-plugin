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


## Privacy & data

This plugin connects to Convex services and collects anonymous usage data. See the
[Convex privacy policy](https://convex.dev/legal/privacy) for full details and your rights.
Three kinds of data can leave your machine, each governed by a rule that holds no matter
which command triggers it:

### 1. Anonymous usage telemetry (on by default, opt-out)

Hooks may send anonymous telemetry to Convex's PostHog project: a random device id, the
plugin version, your OS, and coarse event names (session start, lint/typecheck counts).
Never your code, file paths, prompts, or personal identifiers. Opt out with
`CONVEX_PLUGIN_TELEMETRY=0` or `DO_NOT_TRACK=1`.

### 2. Building your app (only when you invoke a scaffolding flow)

Flows that scaffold or extend an app (such as `quickstart` and `/add`) send the inputs you
give them to the Convex scaffolding service so it can build for you — for example, the
one-sentence idea you type is sent to the scaffolding endpoint and logged as a run start.
These flows also download and run setup scripts from that service. This happens only when
you invoke such a flow.

### 3. Sharing a session to improve the tools (one-time, explicit opt-in)

Some flows can offer to send a **redacted** copy of your current session to the Convex team to
help improve these tools. This is **opt-in and asked once**: the first time it would send,
you're asked to choose **Always**, **Just this once**, or **Never**. *Always* and *Never* are
remembered per user (stored in `~/.convex/improve-consent`) so you're not asked again; *Just this
once* shares only that session and isn't stored, so a later session asks again. **Nothing is sent
until you've explicitly chosen to share**: the flow is built to ask first, and the skill instructs
the agent not to answer on your behalf. For a hard guarantee that nothing is ever sent, set
`CONVEX_IMPROVE_CONSENT=never` — it's an absolute kill switch that overrides any stored choice.
Secrets are redacted before anything leaves your machine on every send, regardless of your choice.
Change your mind anytime by deleting `~/.convex/improve-consent` or setting that variable.

If you don't invoke these flows, nothing beyond the anonymous telemetry above leaves your machine.
## License

Apache-2.0

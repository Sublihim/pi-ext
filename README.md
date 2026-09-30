# pi-ext (personal fork)

Personal fork of [tomsej/pi-ext](https://github.com/tomsej/pi-ext), pruned to the
extensions actually used here. Upstream credit and the MIT license are retained.

## Why a fork

Upstream declared Pi-provided packages (`@earendil-works/*`, `@mariozechner/*`,
`typebox`) in `dependencies`. Pi then warns that installed copies can bypass the
extension loader and create duplicate runtime modules. Here those packages live
in `peerDependencies` with a `"*"` range, which is what Pi expects.

Removed as unused or tied to a different toolchain:

- `pi-sem` and the `sem` skill, plus the optional `@ataraxy-labs/sem` dependency
  — semantic git tooling.
- `pi-cloak`.
- The whole `wf` contract-driven workflow: the `wf-gate` extension, the `wf/`
  gate runner, the `wf-*` skills and `prompts/wf.md`. It is built around git
  worktrees, GitHub PRs and the `super.engineering` CLI, none of which apply here.
- The `Contracts` group in `leader-key`, which only ever called `wf-gate.mjs`.
- Unused dependencies `@benvargas/pi-claude-code-use`, `@tintinweb/pi-tasks` and
  `js-yaml` (only `wf-gate.mjs` used it).

## What is kept

| Extension | Purpose |
|---|---|
| custom-footer | Powerline-style status bar |
| leader-key | `Ctrl+X` command palette |
| tool-pills | Compact tool output, syntax-highlighted diffs |
| tool-trim | Deactivate prompt-expensive tools |
| review | `/review` command |
| handoff | `/handoff` — worktree plus full session fork |
| worktime | `/worktime` active-time tracker |
| pi-vcc | Algorithmic compaction and `vcc_recall` |

Skills: `pr-review-comments`, `pr-explain`, `review-guards`.
Theme: `catppuccin-mocha`.

## Install

```bash
pi install git:github.com/<your-user>/pi-ext
```

## License

MIT © tomsej

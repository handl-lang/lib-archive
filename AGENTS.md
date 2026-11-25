# lib-archive

`archive` — Handl stdlib port (pure handl). Single-module package: the
whole library is `src/index.hnl`.

## Layout

| path | role |
| --- | --- |
| `src/index.hnl` | the library (pure handl) |
| `pkg.hnl` | package manifest — `modules: ["archive"]`, license, keywords |
| `scripts/hnl-gate.sh` | the gate — `hnl typecheck`/`lint`/`test` over `src/**/*.hnl` |
| `workflows/gate.yaml` | CI — shared `handl-gates` campaign (bupha/peregrin) |

## Contract

- Pure `.hnl`, no Rust crate — consumers vendor `pkg.hnl` + `src/**/*.hnl`
  via `handl-pkg-vendor`.
- Sibling deps, when declared in `pkg.hnl`, are git deps on `branch:main`.

## Verification

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
```

The gate only covers canonical `.hnl` dialect; arrow/contract-dialect
files (`cap`/`op`/`~>`) are detected and skipped by the script.

<!-- myco:agent-awareness -->

## Agent awareness

- Session start / any work discussion: run `myco status --prompt`
  before proposing next steps — know the board first.
- User describes new work → offer to capture it (`myco todo add`,
  `issue new`, `proposal new`). Don't wait to be asked.
- Picking up a task: `myco resume <ID>` is the briefing.
- Wrapping up: `myco handoff <ID>` anything resumable; keep statuses
  honest (claimed → in-progress → blocked/done).

<!-- /myco:agent-awareness -->

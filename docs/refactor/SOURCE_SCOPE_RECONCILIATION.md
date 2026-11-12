# Source Scope Reconciliation — DESIGN.md and Previous OpenSpec Refactor

## Chronology and preservation

1. The first OpenSpec change was created using the GitHub README as the only directly available original design/proposal source.
2. User subsequently supplied the complete [DESIGN.md](../../DESIGN.md) (stored without intentional edits) and the original [智慧停車提案解析.pdf](../submission/智慧停車提案解析.pdf).
3. The [original README snapshot](../baseline/README_BEFORE.md) remains unchanged for a valid audit of what was actually available at the earlier refactor step.
4. Earlier [INTRODUCTION.md](../research/INTRODUCTION.md) and [RELATED_WORK.md](../research/RELATED_WORK.md) were not previously aligned line-by-line to the newly uploaded DESIGN.md. Any resulting cross-city inconsistencies require a distinct source-based revision.

## Material distinctions in uploaded DESIGN.md

| Aspect | Uploaded DESIGN.md | Earlier proposal README/academic rewrite | Required treatment |
| --- | --- | --- | --- |
| Primary real-time system | **Taichung** information Agent, GIS, persistence/scheduler, future predictions **DISABLED** | **New Taipei** roadside arrival-time proposed Agent | Distinguish deployed prototype from proposed New Taipei study |
| Historical modeling | New Taipei JSONL Phase 2, +30/+60-minute offline comparison | New Taipei prediction proposed, exploratory MAE≈7.12 source claim | Keep both with provenance; do not present either as a shared test |
| Reported Phase 2 metrics | Persistence MAE 0.326757; RF 0.402669; HistGB 0.537539, common 9,178,935 test rows | Generic H1 that candidate model may beat Persistence | Report H1 as **not supported by uploaded DESIGN.md's aggregate offline comparison** rather than assume model superiority |
| Trust boundaries | Phase 2 conditionally trustworthy; nominal split boundary target crossing; source freshness unavailable in Taichung payload | Full-data experiments and online recommendation not verified | Evidence indicates a measured offline experiment in another workspace, but underlying reports/data absent here; not independently reproduced |
| Final service | Taichung current-information only, unknowns and abstention; forecasting disabled | Risk-aware Top-k arrival-time New Taipei service is proposed | Do not imply arrival-time Agent in production |

## Source-level implementation claims, not code verification

The supplied DESIGN.md references `PHASE2_REPORT.md`, `PHASE3_REPORT.md`, `web/backend/app.py`, `src/agent/taichung_mvp.py`, capture scripts and other outputs. These paths are **not all in this repository**. A report or path referenced in DESIGN.md is not a substitute for running its implementation or independently validating its metrics.

## Follow-up work and status

- **DONE**: source files preserved, source scope conflict made visible, README links updated.
- **PARTIAL**: earlier A–F / Introduction / Related Work document refactor exists but predates the uploaded DESIGN.md.
- **PENDING**: explicit rewrite of Introduction / Related Work using the DESIGN.md as ground truth, with New Taipei vs Taichung clearly disambiguated.
- **NOT RUN**: OpenSpec CLI validation and full original data/model tests.

## Attachment integrity

- Original user-provided PDF size: 255,236 bytes.
- Original PDF SHA-256: `f8d883960ae8fd903e57bd037bf6cff55c1cb253e331ec6334cf0c9fdc550a12`.
- PDF was uploaded as a Git binary blob, not a text transcription.

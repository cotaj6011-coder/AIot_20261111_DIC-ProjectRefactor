# Primary Source and Scope Reconciliation — Reviewed 2026-11-13

## Source hierarchy and document types

| File | Source type | What it proves | What it does not |
| --- | --- | --- | --- |
| [Original New Taipei DOCX](../submission/智慧停車AI_Agent_Proposal_新北市%281%29.docx) | **Primary submitted proposal, 11 pages** | Original A–F, §1 Introduction, §2 Related Work, §3 5/3/10, §4 Agent, §5–7 QA/evaluation/status, original [5]–[13] references | Does not by itself prove all proposed experiments completed |
| [Original DESIGN.md](../../DESIGN.md) | **Design and subsequent progress narrative** | States separate Taichung Agent implementation and New Taipei Phase 2/2.5 offline evaluation results, timeline and limitations | Cannot verify missing code, trained models or test logs |
| [Original proposal analysis PDF](../submission/智慧停車提案解析.pdf) | **Prior analysis / infographic source, 4 pages** | Records proposal diagnostic, chart mapping and preliminary states at time created | Earlier analysis should not override later actual DESIGN results or prove completed experiments |
| [README before OpenSpec](../baseline/README_BEFORE.md) | **Snapshot of repository's initial summary** | Audit trail for what earlier ChatGPT refactor actually used | Not a substitute for original DOCX and DESIGN |
| [OpenSpec change](../../openspec/changes/refactor-smart-parking-proposal/proposal.md) | **Planning and audit artifact** | Requirements, design choices, tasks and documentary changes | Not native CLI validation or empirical proof |

## City and phase separation

| Stage | Geographic target | Artifact evidence | Methodological conclusion |
| --- | --- | --- | --- |
| Proposal and early notebook | **New Taipei roadside** | Original DOCX §5.1 | Reports sample MAE ~7.12, segment ID not in sample model. **Not comparable** to later Phase 2 metrics. |
| Phase 2 offline | **New Taipei roadside** | DESIGN.md §10 | Source-reported 9,178,935 common test observations and persistence MAE 0.326757 outperforming RF 0.402669 and HistGB 0.537539 on aggregate. **No underlying run in this repo**. |
| Phase 2.5 critique | **New Taipei roadside** | DESIGN.md §11 | Unchanged-target prevalence and nominal split-boundary target crossing; trust is conditional. No production model ready. |
| Phase 3–4.6 | **Taichung current-information Agent** | DESIGN.md §§12–15 | Agent, snapshots, GIS/scheduling and failure-handling described as implemented elsewhere. Forecasting DISABLED. |
| Proposed arrival-time risk-aware service | **New Taipei roadside** | Original DOCX §§1,4,6 | H2/H3 and deployment of future-arrival Top-k remain planned; cannot borrow Taichung's current-information status as proof. |
| QA comparison | **Birmingham off-street garages** | Original DOCX §5.3 / UCI | External dataset and QA methodology, not a Taiwan roadside benchmark. |

## Conflicting historical status texts

- The first README and DOCX say New Taipei full QA/model evidence is still planned. Subsequent DESIGN.md reports offline Phase 2/2.5 having been performed elsewhere. **Resolve by naming provenance and stage**, not deleting historical wording or saying the two documents are identical.
- Original proposal H1 predicted a tree-model advantage. The subsequent report gives Persistence the aggregate MAE lead. **H1 is unsupported on these source-reported aggregate tests**; no claim of an independent statistical rejection without raw rows or uncertainty estimates.
- Taichung's **information-only** Agent has no validated future occupancy model. Roadside observed count, off-street signal, estimated direct-line distance, and unknown fields retain separate evidence labels.
- The experiment's **nominal boundary crossing** is a documented methodological limitation. Even when the source states no test leakage, next evaluation must purge target windows crossing splits; do not claim fully leakage-free cross-validation solely from nominal 60/20/20.
- Original PDF infographic's planned/implemented labels were created before full source reconciliation; do not silently rewrite the immutable PDF.

## After-review follow-up

**Completed now:** Source files linked; research chapters rewritten based on exact DOCX §1–§2 and DESIGN §§9–15; all original nine bibliographic entries audited and reconciled; before/after map and evidence statuses updated.

**Still blocked/not run:** Actual model logs/full JSONL/PHASE reports absent here; no native `openspec validate`; original PPTX optional/not in GitHub, no explicit Git duplication requirement established; LMS formal requirements not independently inspected.

## Source preservation

The source DOCX, PDF, DESIGN.md and baseline README are kept as historical inputs. No original data/model reports were invented or copied from other cities.

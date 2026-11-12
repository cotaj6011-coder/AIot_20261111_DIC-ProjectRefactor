# Change Proposal: Source-Aligned Smart Parking Research Refactor

## Why

The DIC3 exercise calls for a **specification-driven refactor of a previously prepared research proposal**, not just a repository of OpenSpec Skills. The initial academic rewrite was based on README because original artifacts had not yet been uploaded. With the later original New Taipei DOCX and DESIGN.md now present, this change must correct research-stage conflation, restore all nine original studies and provide defensible before/after evidence.

## What Changes

- Preserve immutable original proposal DOCX, DESIGN.md, analysis PDF and initial README snapshot.
- Trace A–F, five core mindsets, three controversies, ten questions, Introduction and Related Work to the original DOCX.
- Refactor Introduction and Related Work to preserve New Taipei as the research study, while isolating Taichung's information-only implementation.
- Reconcile original sample MAE (~7.12) with **different**, later DESIGN.md Phase 2 source-reported aggregate MAEs (Persistence 0.326757, RF 0.402669, HistGB 0.537539). Preserve Phase 2.5 limitations and H1 source-reported non-support.
- Audit **all original references [5]–[13]** against identifiable publisher/dataset URLs.
- Correct OpenSpec delta-spec headings, evidence labels, and README/Acceptance links; keep unreproducible research and native CLI verification as NOT RUN.
- Supply a source-section-based before/after table and explicit unresolved items.

## Capabilities

### New Capabilities
- `research-proposal-refactor`: Deliver a traceable, verifiable, evidence-first academic proposal refactor aligned with the original 11-page New Taipei DOCX and later design material.

### Modified Capabilities
- None. No existing canonical capability specifications were present under `openspec/specs/` in the audited repository.

## Impact

- Documentation and OpenSpec change artifacts only: `docs/research/`, `docs/references/`, `docs/refactor/`, `README.md`, and `openspec/changes/refactor-smart-parking-proposal/`.
- No source code, model weights, experiments, original DOCX/PDF, or source DESIGN.md are edited.
- The OpenSpec CLI was **not run** by the GitHub Connector; static inspection is not an official validation result.

## Evidence and scope

1. [Original New Taipei proposal DOCX](../../../docs/submission/智慧停車AI_Agent_Proposal_新北市(1).docx), 11 pages.
2. [Original DESIGN.md](../../../DESIGN.md), §§9–15 include later cross-city development and offline model comparisons.
3. [Original proposal-analysis PDF](../../../docs/submission/智慧停車提案解析.pdf), four pages.
4. [Pre-refactor README snapshot](../../../docs/baseline/README_BEFORE.md) from `f060df0569667769c9053b7affe87265cfeb415f`.
5. [Citation audit](../../../docs/references/REFERENCE_AUDIT.md) and the original [5]–[13] DOI list.

Source-specific evidence classes: **repo-verified document**; **source-reported implementation/evaluation not reproduced here**; **planned**; **blocked**. These must never be collapsed into a single unqualified PASS.

## Success criteria

- Nine delta requirements have official OpenSpec-compatible header structure and WHEN/THEN scenarios.
- DOCX §1–§3 and [5]–[13] are explicitly mapped to revised sections and references.
- Revised Introduction and Related Work do not misattribute Taichung source-reported implementation to New Taipei production.
- H1 is not falsely reported as passed; Phase 2 offline findings and split-boundary risk are disclosed.
- All nine publication/dataset entries have working landing-page references checked at least at bibliographic/abstract level.
- Manual acceptance is evidence-mapped, with native CLI and code/runtime experiments marked NOT RUN.

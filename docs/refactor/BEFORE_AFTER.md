# Before / After Audit — Original DOCX and DESIGN Aligned

**Original sources remain unchanged:** [Proposal DOCX](../submission/智慧停車AI_Agent_Proposal_新北市%281%29.docx), [DESIGN.md](../../DESIGN.md), [Proposal Analysis PDF](../submission/智慧停車提案解析.pdf), and [Original README snapshot](../baseline/README_BEFORE.md) from commit `f060df0569667769c9053b7affe87265cfeb415f`.

**Chronology:** Earlier academic refactor preceded the source DOCX/DESIGN uploads, so this new audit links **actual original sections** to revised deliverables. Do not describe the later uploaded DESIGN.md as a document whose content was itself rewritten; only derived academic chapters and OpenSpec audit records were revised.

| Source | Original issue or contract | Refactored artifact | Verified improvement / status |
| --- | --- | --- | --- |
| DOCX §Abstract A–F (p.2) | Initial 7.12 sample in Findings; full QA still described as Planned | [ABSTRACTS](../research/ABSTRACTS.md) | Separates sample 7.12 from later source-reported offline Phase 2, avoids false completed deployment |
| DOCX §1.1–1.2 (pp.2–3) | Why arrival matters; input/output contract | [INTRODUCTION](../research/INTRODUCTION.md) §§A–B | Explicit decision cutoff `t`, arrival horizon `h`, provenance and quality |
| DOCX §1.3 (p.3) | Empirical data gap vs integration gap | [INTRODUCTION](../research/INTRODUCTION.md) §C | Bounds project-level claim; recognizes prior uncertainty/integration work |
| DOCX §§1.4–1.5 (p.3) | H1–H3 and Agent need | [INTRODUCTION](../research/INTRODUCTION.md) §D | Discloses Persistence best on source-reported Phase 2 aggregate; requires fixed pipeline for H3 |
| DOCX §1.6 (pp.3–4) | Claimed contributions and prototype status | [INTRODUCTION](../research/INTRODUCTION.md) §§E–F | Distinguishes intended New Taipei contributions from Taichung source-reported implementations |
| DOCX §2.1 (p.4) | Mixed statistical, spatial, Bayesian methods | [RELATED_WORK](../research/RELATED_WORK.md) §§A–D | Critical taxonomy with unit/horizon transfer constraints |
| DOCX §2.2 (pp.4–5) | Original **nine** references [5]–[13] | [RELATED_WORK](../research/RELATED_WORK.md) §E + [REFERENCE_AUDIT](../references/REFERENCE_AUDIT.md) | **9/9** original reference identifiers located/checked on publisher or dataset pages |
| DOCX §3.1–3.3 (pp.5–6) | 5 mindsets / 3 controversies / 10 questions | [RESEARCH_5_3_10](../research/RESEARCH_5_3_10.md) | Explicit item-to-method mapping and decision criteria |
| DOCX §4.1–4.3 (pp.6–7) | Planner/tool/validation/pseudocode | [INTRODUCTION](../research/INTRODUCTION.md) §§B,D–E | Proposed New Taipei workflow separate from implemented Taichung current-information Agent |
| DOCX §§5–7 (pp.7–10) | Original New Taipei QA plans, H1 targets, reported 9 tests | [INTRODUCTION](../research/INTRODUCTION.md) §E + [SOURCE_SCOPE](SOURCE_SCOPE_RECONCILIATION.md) | Temporal purge requirement and evidence classes; no invented new tests |
| DESIGN.md §10 | Later offline metrics, **Persistence best** | [INTRODUCTION](../research/INTRODUCTION.md), [ABSTRACTS](../research/ABSTRACTS.md) | Corrects older text stating all offline experiments unrun |
| DESIGN.md §11 | Label crossing, unchanged occupancy and conditional trust | [INTRODUCTION](../research/INTRODUCTION.md), [SOURCE_SCOPE](SOURCE_SCOPE_RECONCILIATION.md) | No blanket production-ready or perfect temporal split claims |
| DESIGN.md §§12–15 | Taichung Agent/operations | [INTRODUCTION](../research/INTRODUCTION.md) §E + [SOURCE_SCOPE](SOURCE_SCOPE_RECONCILIATION.md) | Taichung current-information vs New Taipei predictive service separated |
| Prior OpenSpec docs | Old citations and missing-document status | [OpenSpec Change](../../openspec/changes/refactor-smart-parking-proposal/proposal.md), [Acceptance](ACCEPTANCE.md) | Update after new source uploads; CLI still NOT RUN |

## Important non-equivalences

1. Original DOCX is a **proposal**, later DESIGN contains an **offline experiment narrative** and **Taichung implementation narrative**.
2. MAE 7.12 (sample) and 0.326757 (later Phase 2) are different experiments, **not a same-split before/after improvement**.
3. Implemented/Evaluated in a **source file** does not imply independently reproduced from this documentation-only GitHub repo.
4. SFpark 43% and 30% are external parking policy evidence, **not this system's outcomes**.
5. Citation/bibliography verification does not equal reproduced research paper statistics.

## Verification boundary

**Document content comparison: PASS** for a source-based conceptual and section-level audit. **Pixel-perfect or tracked-change DOCX redline: NOT PERFORMED**; native DOCX remains unchanged. **Executable/empirical validation: NOT RUN** within this repository.
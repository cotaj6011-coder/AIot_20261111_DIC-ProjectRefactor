# OPENSPEC_MANUAL_VERIFICATION — DIC3 Smart Parking Proposal Refactor

**Date:** 2026-11-13 (Asia/Taipei)  
**Repository:** [AIot_20261111_DIC-ProjectRefactor](https://github.com/cotaj6011-coder/AIot_20261111_DIC-ProjectRefactor)  
**Change:** `openspec/changes/refactor-smart-parking-proposal/`  
**GitHub baseline audited:** `6de065264bfe3470fb93274dc6c8a46ec7938c6d` (the head before this manual verification commit).

> **Verification type: GitHub Connector + manual static document inspection only.** No terminal, no native OpenSpec CLI, no model execution, no external LMS access. **`openspec validate`: NOT RUN.** A documentary PASS is *not* a CLI/experimental PASS.

## 1. Explicit workflow: Proposal → Specs → Design → Tasks → Apply → Verify

| Stage | Artifact and evidence | Review result | Validation boundary |
| --- | --- | --- | --- |
| **Proposal** | [Change proposal](../../openspec/changes/refactor-smart-parking-proposal/proposal.md) declares why, changes, scope, impact and `research-proposal-refactor` capability | **PASS — documentation** | No CLI status output |
| **Specs** | [Delta spec](../../openspec/changes/refactor-smart-parking-proposal/specs/research-proposal-refactor/spec.md) has `## ADDED Requirements`, nine `### Requirement:` and nine `#### Scenario:`, each with WHEN/THEN | **PASS — static schema shape** | Official OpenSpec parse/strict validation NOT RUN |
| **Design** | [Change design](../../openspec/changes/refactor-smart-parking-proposal/design.md) explains source hierarchy, city boundary, evidence, temporal purging and decisions | **PASS — documentation** | Not an executable system design verification |
| **Tasks** | [Tasks](../../openspec/changes/refactor-smart-parking-proposal/tasks.md) enumerates completed documentary outputs and unrun CLI/science tasks separately | **PASS — documentation** | Some external dependencies remain |
| **Apply** | [Introduction](../research/INTRODUCTION.md), [Related Work](../research/RELATED_WORK.md), [Abstracts](../research/ABSTRACTS.md), [5/3/10](../research/RESEARCH_5_3_10.md), [Reference Audit](../references/REFERENCE_AUDIT.md), [Before/After](BEFORE_AFTER.md) are committed | **PASS — documentary application** | Original binary files preserved, not edited |
| **Verify** | This requirements matrix, [Acceptance](ACCEPTANCE.md), final GitHub file and link checks | **PASS — manual static document checks** | Native `openspec validate` **NOT RUN** |

## 2. Requirement/Scenario-by-Scenario Evidence

These **nine documentary scenarios** are checked against the complete text of [spec.md](../../openspec/changes/refactor-smart-parking-proposal/specs/research-proposal-refactor/spec.md). `PASS` means **the described document contract is presently evidenced**; it does not assert software behavior or independent replication of performance.

| ID | Requirement → Scenario | Manual verification method | Evidence | Documentary status | Additional caveat |
| --- | --- | --- | --- | --- | --- |
| **R1** | **Primary-source traceability** → reviewer checks revised sections | Confirm original DOCX, PPTX, DESIGN, PDF, baseline README Git objects exist; inspect mapping from DOCX §§1–3 to rewritten chapters | [Original DOCX](../submission/智慧停車AI_Agent_Proposal_新北市%281%29.docx), [PPTX](../submission/智慧停車AI_Agent_Proposal_新北市%281%29.pptx), [DESIGN](../../DESIGN.md), [PDF](../submission/智慧停車提案解析.pdf), [Before/After](BEFORE_AFTER.md) | **PASS** | DOCX tracked-changes redline was not generated; comparison is section-level |
| **R2** | **A–F academic argument** → A–F abstract inspection | Read six explicit A–F entries, confirm sample 7.12 is not equated to later Phase 2 0.326757 | [Abstracts](../research/ABSTRACTS.md), [5/3/10 A–F table](../research/RESEARCH_5_3_10.md) | **PASS** | Proposed new abstract not known to replace previously submitted LMS version |
| **R3** | **Five-three-ten research analysis** → review analysis count | Count enumerated mindsets = **5**, controversies = **3**, deep questions = **10**, review their evidence/evaluation implications | [RESEARCH_5_3_10](../research/RESEARCH_5_3_10.md), original DOCX §3 and PPTX slides 5–7 | **PASS** | Academic quality remains subject to teacher assessment |
| **R4** | **Academically bounded Introduction** → evaluate city scope | Check New Taipei roadside proposed service is distinct from Taichung current-information Agent; Persistence's reported baseline lead is disclosed | [Introduction](../research/INTRODUCTION.md) §§A–F; [Source scope](SOURCE_SCOPE_RECONCILIATION.md); [DESIGN](../../DESIGN.md) §§9–15 | **PASS** | No live New Taipei deployment evidence |
| **R5** | **Full source-aligned Related Work** → source table audit | Compare paper/table labels **[5]–[13]** to original DOCX §2 and its References; verify all nine have DOI or dataset landing page in audit | [Related Work](../research/RELATED_WORK.md) §E; [Reference Audit](../references/REFERENCE_AUDIT.md) | **PASS** | Citation metadata/abstract review is not full paper or experimental replication |
| **R6** | **Reproducible evaluation protocol** → temporal label boundary | Inspect specification for time cutoff `t`, future target `t+h`, purging nominal split crossings, missing-label treatment, and matched benchmarks | [Introduction](../research/INTRODUCTION.md) §E; [Change Design](../../openspec/changes/refactor-smart-parking-proposal/design.md); [DESIGN](../../DESIGN.md) §11 | **PASS — planned protocol** | **NOT RUN** corrected purged re-evaluation; older source-reported Phase 2 has boundary caveat |
| **R7** | **Evidence-state precision** → two MAE claims | Locate source/phase-qualified MAE `7.12`, `0.326757`, `0.402669`, `0.537539`; confirm H2/H3 not represented as achieved | [Abstracts](../research/ABSTRACTS.md), [Introduction](../research/INTRODUCTION.md), [Source scope](SOURCE_SCOPE_RECONCILIATION.md), [Design](../../DESIGN.md) | **PASS** | Metrics reported in original material; not reproduced by this repository |
| **R8** | **Honest OpenSpec validation status** → review change completeness | Confirm all four OpenSpec stages present, README and Acceptance reachable, and all CLI statements explicitly say NOT RUN | [README](../../README.md), [Tasks](../../openspec/changes/refactor-smart-parking-proposal/tasks.md), [Acceptance](ACCEPTANCE.md), this document | **PASS** | Native `openspec validate`: **NOT RUN** |
| **R9** | **Submission boundary clarity** → PDF/PNG submission location | Confirm proposal PDF retained as source and no ungrounded requirement that LMS PNG/PDF be duplicated in Git is claimed | [README](../../README.md), [Change proposal](../../openspec/changes/refactor-smart-parking-proposal/proposal.md), [PDF](../submission/智慧停車提案解析.pdf) | **PASS — qualified wording** | Teacher's formal LMS upload/filename rules **BLOCKED** from GitHub alone |

**Documentary requirement coverage: 9/9 (100%) manually checked as present and aligned.** This rate measures the **nine specified document scenarios only**. It does **not** measure assignment grading, OpenSpec CLI validity, API behavior, machine-learning success, H2/H3, source-code correctness or model production readiness.

## 3. Static structural verification and source preservation

| Check | Evidence | Outcome |
| --- | --- | --- |
| GitHub tree | Connector read of commit `6de065264bfe3470fb93274dc6c8a46ec7938c6d` | **PASS: 32 repository blobs** |
| Authored Markdown (excluding Skills and baseline snapshot) | 15 text files retrieved via GitHub Connector | **PASS: 15 read** |
| Local relative Markdown links | 94 destinations resolved against GitHub tree after percent-decoding, with anchor fragments excluded from path | **PASS: 0 broken local file links** |
| External URLs in Markdown | 11 URL occurrences inspected as text | **PRESENCE ONLY**: link reachability not tested in this static pass |
| OpenSpec `### Requirement:` / `#### Scenario:` | Parse heading counts and check every scenario has WHEN/THEN and norm SHALL | **PASS: 9 requirements / 9 scenarios / 9 complete WHEN+THEN** |
| 5/3/10 enumeration | Count numbered entries inside their corresponding headings | **PASS: 5 / 3 / 10** |
| Literature audit IDs | Scan labels `[5]` through `[13]` in reference audit | **PASS: 9/9 labels present**; source metadata verification is recorded in a separate prior audit |
| Original DOCX binary | Git SHA `d9403f1175247ef59d35591bb5ded4e8104db9f0`, 46,881 bytes | **PASS — unchanged Git object** |
| Original PPTX binary | Git SHA `4a14c32d115a0a9bd45c53425ee850401a2bb259`, 77,376 bytes | **PASS — unchanged Git object** |
| Original proposal PDF binary | Git SHA `448dee966a35d0e3fea59c7966c5a32f9cc4582f`, 255,236 bytes | **PASS — unchanged Git object** |
| Original DESIGN.md | Git SHA `945c587bc0c8251ad9888db1ba6c8212ea166eb3`, 11,496 bytes | **PASS — unchanged Git object** |
| Original README snapshot | Git SHA `217ebe6cd248a65c7352b82d0d12289b892434b2`, 9,527 bytes | **PASS — unchanged Git object** |

**Method qualification:** Repository hashes establish no modification of original committed assets relative to the preceding commit. They do not independently authenticate that each originally supplied source matches an external institutional original. Markdown links were validated for **file target existence only**, not for external HTTP response or fragment anchors.

## 4. Research integrity and known unresolved work

| Topic | Result | Evidence / why incomplete |
| --- | --- | --- |
| **New Taipei original proposal** | **PASS documentary alignment** | DOCX defines roadside arrival-time prediction and risk-aware recommendation as prospective study |
| **Taichung Agent** | **PASS source-stage distinction** | DESIGN §§12–15 reports **current-information-only** Agent; future forecasting DISABLED |
| **New Taipei Phase 2 offline** | **SOURCE-REPORTED / NOT REPRODUCED HERE** | DESIGN reports persistence aggregate MAE 0.326757 vs RF 0.402669 / HistGB 0.537539 on 9,178,935 common test rows |
| **H1** | **PARTIAL / source-reported evidence contrary to tree superiority** | Reported aggregate benchmark favors Persistence; target-crossing purge and independent rerun pending |
| **H2** | **PLANNED / NOT RUN** | No calibrated arrival-time Top-3 outcome experiment in repo |
| **H3** | **PLANNED / NOT RUN** | No matched fixed-Pipeline versus Agent fault-injection experiment in repo |
| **Model calibration and production SLA** | **NOT RUN** | No reproducible model/code/test suite, no validated live production New Taipei predictions |
| **Citation verification** | **PASS bibliographic subset audit; not statistical replication** | See [nine-entry reference audit](../references/REFERENCE_AUDIT.md); URLs not re-fetched in this pass |
| **LMS assignment / submission** | **BLOCKED** | Formal iLearning rubric and actual upload state unavailable to GitHub Connector |
| **Official OpenSpec CLI** | **NOT RUN** | Neither `openspec init` nor `openspec validate` was executed; this is an explicit no-CLI workflow |

## 5. Disposition and final decision

**Documentary OpenSpec change: PASS (manual file/structure/content contract)** — all nine delta-spec documentary scenarios have direct evidence; recorded workflow is Proposal → Specs → Design → Tasks → Apply → Verify.

**Official OpenSpec validation: NOT RUN. Research performance readiness: NOT ESTABLISHED. Formal instructor grading/compliance: NOT independently verified.**

The manual verification report is a traceability artifact intended to help a reviewer check the work without claiming more than the repository demonstrates. **This file should not be presented as a substitute for native CLI validation if such evidence is an explicit grading requirement.**

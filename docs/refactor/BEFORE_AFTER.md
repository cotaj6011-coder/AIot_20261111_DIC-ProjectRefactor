# Before / After Refactor Traceability

**Baseline commit:** `f060df0569667769c9053b7affe87265cfeb415f`. A full textual snapshot of root `README.md` is at [README_BEFORE.md](../baseline/README_BEFORE.md). This document describes the specific **README-derived** refactor; it does NOT pretend that the original DOCX/PPTX or standalone DESIGN.md were available in the repository.

| Starting README | Observed content / risk | Refactored destination | Change rationale |
| --- | --- | --- | --- |
| §1 Project overview | Present-vs-arrival insight, features but insufficient formal research framing | [Introduction](../research/INTRODUCTION.md) §§A–C | Defines operational question, bounded research gap and explicit scope |
| §2 Agent architecture | Diagram with conceptual retry/replan, no experimental proof of benefit | [Introduction](../research/INTRODUCTION.md) §§D–E | Reframes agent's necessity as H3 versus fixed Pipeline |
| §3 Data sources | Source-reported New Taipei JSONL, sampled MAE 7.12, Bangalore/Birmingham prototype | [Introduction](../research/INTRODUCTION.md) §F and [Reference Audit](../references/REFERENCE_AUDIT.md) | Distinguishes claims, provenance and missing reproducible evidence |
| §4 Baselines and models | Candidate methods without critical literature synthesis | [Related Work](../research/RELATED_WORK.md) §§A–D | Links methods to identifiable publications and boundaries |
| §5 H1–H3 | Hypotheses listed as Planned | [Introduction](../research/INTRODUCTION.md) §D | States falsifiability, controls, outcome definitions |
| §6 Evaluation plan | Chronological split stated; overlap purge not explicit; metric list disconnected from hypotheses | [Introduction](../research/INTRODUCTION.md) §E and [OpenSpec Specs](../../openspec/changes/refactor-smart-parking-proposal/specs/research-proposal-refactor/spec.md) | Adds cutoff/purge boundaries, metric-to-hypothesis traceability |
| §7 Prototype progress | “Implemented/Verified” may be mistaken as verified within this repo | [Research 5/3/10](../research/RESEARCH_5_3_10.md) and [Acceptance](ACCEPTANCE.md) | Separates self-reported external prototype from GitHub-verifiable docs |
| §8 References | Six named scholarly/data references and a TDX entry, incomplete full paper coverage | [Related Work](../research/RELATED_WORK.md), [Reference Audit](../references/REFERENCE_AUDIT.md) | Checks selected DOIs and declares unresolved items |
| No stand-alone abstracts | Initial README is not an A–F academic abstract | [Abstracts](../research/ABSTRACTS.md) | Adds ~300-character Chinese and 1-paragraph prospective IEEE style |
| No 5/3/10 document | Insights scattered through README | [5/3/10](../research/RESEARCH_5_3_10.md) | Provides exactly 5 mindsets, 3 trade-offs, 10 testable questions |
| No documented OpenSpec Change | Only Skills/config existed | [Change proposal](../../openspec/changes/refactor-smart-parking-proposal/proposal.md) | Makes requirements/decision/tasks reviewable |

## Research integrity changes

- Avoids using SFpark as this proposed Agent's outcome.
- States R2–R4 as prior studies of spatial/uncertain parking forecasting, so claimed novelty is **joint risk-aware Agent evaluation**, not the first such algorithm.
- Converts “model feasibility” from MAE≈7.12 to an **unreproduced exploratory source claim**.
- Distinguishes requested GitHub *documentation* refactor from absent experimental software.
- Uses a source-first policy; the “nine papers” described by proposal analysis is not reconstructed from thin air.

## Still missing for a full original-design diff

1. Source `DESIGN.md` and original DOCX/PPTX from the initial final project.
2. Full original Related Work nine-paper bibliography/table and original Introduction exact text.
3. Actual New Taipei data and notebook / validation reports.
4. Formal LMS written submission requirements and any required filenames.

**Judgment:** README-based refactor evidence is available; original-DESIGN.md before/after proof remains **BLOCKED**.

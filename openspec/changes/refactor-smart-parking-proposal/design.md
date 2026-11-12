# Document Refactor Design — Source-Grounded and Audit-Ready

## Scope and research framing

This is a **document workflow** for the teacher's OpenSpec demonstration. It does **not** implement or train a new smart parking system. The primary research proposal is New Taipei **roadside-segment future-arrival recommendation** (original DOCX). The separately uploaded DESIGN.md documents later New Taipei **offline modeling** and a distinct Taichung **information-only Agent** with future forecasts DISABLED.

## Evidence pipeline

```text
Original DOCX §§Abstract, 1–7, references [5]–[13]  --+
Original DESIGN.md §§9–15 (later research progress) ----+--> Source / Evidence Matrix
Original proposal-analysis PDF (4 pages) ----------------+         |
Baseline README at f060df0 -----------------------------+         v
                 publisher DOI / dataset checks --> 5/3/10 + A–F
                                                      |
                                           Introduction / Related Work
                                                      |
                            BEFORE_AFTER + REFERENCE_AUDIT + ACCEPTANCE
                                                      |
                                            README for reviewer navigation
```

## Design decisions

1. **Original source integrity:** Preserve original DOCX/PDF/DESIGN and baseline README; only refactored Markdown artifacts and audit metadata change.
2. **H1 handling:** Treat source-reported New Taipei Phase 2 aggregate Persistence MAE as a **counterexample to a guaranteed tree-model improvement**. H1 is unsupported by those source-reported results, but without experiment code/rows no independent reproduction or statistical test is asserted.
3. **Separate experiments:** The early notebook MAE ≈7.12 and later Phase 2 Persistence MAE ≈0.326757 are *not matched comparisons*; their samples, features and splits differ.
4. **Temporal validity:** Source reports target labels crossing nominal split boundaries. Proposed future protocol purges overlapping future-label windows and duplicates, honors feature cutoff t and calibrates on validation only.
5. **H2/H3 evaluation:** Top-3 success uses the first valid observation in a declared post-arrival tolerance; missing truth remains unknown. Compare calibrated risk ranking to distance-only at matched walking constraints/coverage; compare Agent to fixed Pipeline with identical tools and fault injection. Abstention alone is not success.
6. **Uncertainty claims:** BNN uncertainty modeling exists in prior work [11]. Project's freshness and quality penalties are engineering risk proxies, **not** validated epistemic/aleatoric decomposition.
7. **External policy evidence:** SFpark percentages belong to background only, not the project Findings, and cannot be causally attributed to this Agent.
8. **OpenSpec compliance:** Delta spec uses `## ADDED Requirements`, `### Requirement: ...`, and `#### Scenario: ...` with WHEN/THEN lines. No CLI was run in this GitHub-only workflow.

## Traceable outputs

| Artifact | Acceptable evidence |
| --- | --- |
| [INTRODUCTION.md](../../../docs/research/INTRODUCTION.md) | Original DOCX §1.1–1.6 + later DESIGN scope/metrics |
| [RELATED_WORK.md](../../../docs/research/RELATED_WORK.md) | Complete DOCX [5]–[13] study comparison |
| [ABSTRACTS.md](../../../docs/research/ABSTRACTS.md) | A–F with sample/Phase 2 results separated |
| [RESEARCH_5_3_10.md](../../../docs/research/RESEARCH_5_3_10.md) | Exactly five, three, ten |
| [REFERENCE_AUDIT.md](../../../docs/references/REFERENCE_AUDIT.md) | Individual publisher/dataset metadata and claim boundaries |
| [BEFORE_AFTER.md](../../../docs/refactor/BEFORE_AFTER.md) | Source heading → revised heading matrix |
| [ACCEPTANCE.md](../../../docs/refactor/ACCEPTANCE.md) | PASS/PARTIAL/FAIL/BLOCKED and NOT RUN with evidence |

## Verification method and remaining limits

Use GitHub Connector to confirm the files and links exist and compare referenced source headings. Perform local/static checks for syntax without calling those checks official `openspec validate`. Actual model/dataset training, official CLI validation, live user-outcome or LMS submission assessment are **outside** this workflow and remain NOT RUN/BLOCKED as appropriate.

# Design — Evidence-Based Academic Proposal Refactor

## Scope

This OpenSpec Change governs **academic documentation**, not a running parking service. The study is New Taipei roadside arrival-time availability and risk-aware Top-k recommendation. `DESIGN.md` also records New Taipei Phase 2 offline model evaluation and a separate Taichung information-only Agent whose future prediction remains disabled.

## Document and evidence flow

```text
Original DOCX / PPTX / DESIGN.md / PDF / README baseline
                          |
                 Source and evidence audit
                          |
        A–F, 5/3/10, Introduction, Related Work
                          |
      Before/After, Reference Audit, Manual Verification
                          |
                    README and Acceptance
```

## Decisions

1. **Preserve provenance.** Original files remain unchanged. Section-level Before/After maps the proposal to revised Markdown.
2. **Handle H1 conservatively.** Source-reported Phase 2 aggregate MAE favors Persistence (0.326757) over RF (0.402669) and HistGB (0.537539). This does not imply a deployment-ready model or independently reproduced experiment.
3. **Keep experiments distinct.** The early sample MAE ≈7.12 has different data/feature conditions and is not a matched comparison with Phase 2.
4. **Control temporal leakage.** Use cutoff-only features, chronological splits and purging of labels crossing nominal partition boundaries. Calibrate only on validation data.
5. **Make H2/H3 testable.** Compare risk-aware Top-3 against distance-only under matched coverage and walking limits; compare Agent and fixed Pipeline using identical tools, faults, recommendation evidence, abstention and latency.
6. **Avoid overclaiming novelty.** Prior work already includes spatial, Bayesian uncertainty and integrated urban parking decision approaches.
7. **Separate cities.** New Taipei research hypotheses cannot be validated by Taichung's existing current-information Agent.
8. **Distinguish validation modes.** Manual document checks are reported separately from native CLI validation. OpenSpec 2.1.0 strict validation is **PASS** with its actual command and JSON output in the [CLI record](../../../docs/refactor/OPENSPEC_CLI_VERIFICATION.md); this does not validate model performance.

## Artifacts and review

| Artifact | Purpose |
| --- | --- |
| [ABSTRACTS.md](../../../docs/research/ABSTRACTS.md) | A–F bilingual academic abstracts |
| [RESEARCH_5_3_10.md](../../../docs/research/RESEARCH_5_3_10.md) | Mindsets, controversies and deep questions |
| [INTRODUCTION.md](../../../docs/research/INTRODUCTION.md) | Research motivation, gap, H1–H3 and evaluation |
| [RELATED_WORK.md](../../../docs/research/RELATED_WORK.md) | Critical original nine-paper synthesis |
| [REFERENCE_AUDIT.md](../../../docs/references/REFERENCE_AUDIT.md) | Bibliography provenance and claims |
| [BEFORE_AFTER.md](../../../docs/refactor/BEFORE_AFTER.md) | Source-to-revision mapping |
| [OPENSPEC_MANUAL_VERIFICATION.md](../../../docs/refactor/OPENSPEC_MANUAL_VERIFICATION.md) | Per-Requirement/Scenario evidence |
| [ACCEPTANCE.md](../../../docs/refactor/ACCEPTANCE.md) | Scope-aware documentary acceptance |

**Validation boundary:** CLI execution is supported only by the linked record. No model execution or LMS submission is implied by this document.


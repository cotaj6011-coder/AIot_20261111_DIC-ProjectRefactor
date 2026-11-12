# Design: Evidence-First Academic Document Refactor

## Architecture

This OpenSpec change governs **documents**, not executable parking software.

```text
original repository README (immutable snapshot)
          + assignment A–F / 5–3–10 criteria
          + proposal analysis / user-supplied abstracts
          + external publication metadata (verified selectively)
                          |
               traceable evidence audit
                          |
          +---------------+------------------+
          |               |                  |
  5/3/10 + A–F     Introduction        Related Work
          |               |                  |
          +---------------+------------------+
                          |
       Bilingual abstract + Before/After + Acceptance
                          |
                README navigation (main)
```

## Academic choices

1. **Research unit**: New Taipei City roadside segments. The existing Taichung information-only Agent and Birmingham prototype are contextual experience, not validated New Taipei arrival-time prediction.
2. **Decision target**: For request time `t` and arrival horizon `h`, estimate available spaces at `t+h` and a calibrated full-occupancy probability if a valid ground truth and enough representative data exist.
3. **Agent necessity**: Compare rule-based fixed pipeline versus planner that can select sources, retry, replan, fallback and abstain under a predeclared fault-injection protocol.
4. **Split design**: Chronological group split with purge/embargo for overlapping observation/label windows, especially near the 60/20/20 boundaries.
5. **Evaluation**: H1 regression MAE/RMSE versus Persistence/Historical Median; H2 risk classification PR-AUC/Brier/ECE and Top-3 arrival success versus distance-only ranking; H3 evidence-less recommendation rate, error coverage, abstention and latency versus a fixed pipeline.
6. **Uncertainty semantics**: Calibration or uncertainty proxies are proposed, not a verified Bayesian epistemic/aleatoric decomposition.
7. **Writing style**: Structure Introduction as background → precise problem → limitations and research gap → questions/hypotheses → contributions → organization. Related Work is critical synthesis, not a paper list or blanket novelty claim.

## Publication integrity

- Citation table contains source-specific claims, DOI and independent check status; no AI-generated fabricated citations.
- SFpark external outcomes, if mentioned, are motivation from parking policy and operations, not this Agent's measured effects.
- Research targets are prospective; acceptance reports paper/document compliance separately from model performance.
- Original DOCX/PPTX and separate DESIGN.md missing from repo are a declared source constraint; `README_BEFORE.md` is an honest baseline, not a substitute claimed to be the full original proposal.

## Artifact contracts

| Artifact | Role |
| --- | --- |
| `docs/baseline/README_BEFORE.md` | Unmodified source snapshot |
| `docs/research/RESEARCH_5_3_10.md` | Five/three/ten and A–F gap analysis |
| `docs/research/INTRODUCTION.md` | Refactored IEEE-like Introduction |
| `docs/research/RELATED_WORK.md` | Comparative literature review |
| `docs/research/ABSTRACTS.md` | Chinese condensed + English scientific abstract |
| `docs/references/REFERENCE_AUDIT.md` | Source and citation confidence |
| `docs/refactor/BEFORE_AFTER.md` | Original-to-refactor mapping and missing evidence |
| `docs/refactor/ACCEPTANCE.md` | Requirement-to-evidence checklist |

## Verification limitations

Textual Markdown and link presence can be independently inspected through GitHub API. The GitHub connector cannot run `openspec validate`, train models, or inspect an absent original file. Mark those items BLOCKED / NOT RUN.

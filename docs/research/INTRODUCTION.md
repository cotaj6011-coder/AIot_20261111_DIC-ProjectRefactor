# I. INTRODUCTION — Refactored Research Proposal

**Working title:** *An Uncertainty-Aware AI Agent for Arrival-Time Parking Availability Prediction and Risk-Aware Recommendation*

> Status: **Proposed study**. Academic prose below describes questions, planned methods and testable contributions. It does not report a finished New Taipei City deployment or definitive experiment.

## A. Background and motivation

Smart parking systems increasingly combine parking observations, information services and forecasting methods to support urban mobility. However, an available space at the time a driver queries an application is not necessarily available when that driver reaches the target street. A recommendation made using stale or unreliable records may also misrepresent conditions even if the prediction model is accurate on clean historical samples. Thus, **arrival-time usefulness**, rather than a stand-alone snapshot or point prediction, is the operational target of this proposal.

The SFpark program illustrates the broader practical importance of better parking information and management: its official evaluation reported reduced search time and circling-related vehicle mileage under a combination of information provision and demand-responsive pricing [R7]. These policy outcomes **must not be attributed to the proposed AI Agent**; they contextualize the societal stakes rather than establish this system's effectiveness.

## B. Problem formulation

We focus on **New Taipei City roadside parking segments**, keeping off-street garages outside the primary scope. At request time `t`, a user supplies destination, expected arrival time `t+h`, walking constraints and parking preferences. For each eligible segment `s`, the proposed decision support system should return the best-grounded available-space estimate `ŷ(s,t+h|information≤t)`, a calibrated estimate of `P(full at t+h)` **if calibration is possible**, source and observation timestamps, a quality indicator, and an interpretable Top-k ranking. If dependable evidence is unavailable, it should fallback or explicitly abstain rather than invent a precise vacancy probability.

This formulation introduces four distinct research problems: (1) irregular, incomplete or erroneous sensor/API observations, (2) temporal dependence and variation across segments and prediction horizons, (3) mismatches between regression error and user-oriented recommendation success, and (4) predictable system failures such as API timeouts, stale readings and low-confidence predictions.

## C. Research gap and scope

The literature already addresses parking time-series prediction, spatiotemporal graph models and Bayesian uncertainty [R1–R5]; hence it would be inaccurate to claim that arrival forecasting or uncertainty-aware parking prediction are absent from prior research. What remains to be **empirically established for this project** is whether a *combined* New Taipei roadside decision workflow—quality gate, horizon-matched baseline and candidate models, risk calibration, failure-aware Agent orchestration and evidence-backed Top-k outputs—improves measurable user-oriented performance over simpler alternatives.

This is a **project-level integration and evaluation gap**, not a claim of a globally unique algorithm. Moreover, the current repository does not include the full New Taipei dataset or notebook, so even data coverage and sample-model performance cannot yet be independently validated here. Specificity of context makes source and horizon alignment essential rather than a trivial implementation detail.

## D. Research questions and falsifiable hypotheses

- **RQ1 / H1 (Prediction):** Under a chronological, leakage-controlled comparison, do models using legal segment/time features lower MAE compared with Persistence? The alternative includes **no improvement**; Historical Median provides an additional baseline. Evaluate by horizon and segment, including rolling-origin robustness.
- **RQ2 / H2 (Recommendation):** Does risk-sensitive ranking that uses calibrated full-occupancy probabilities increase arrival-time Top-3 success by at least the predeclared target relative to distance-only ranking, at comparable coverage and walking constraints? If calibration fails, report this and do not make unjustified confidence claims.
- **RQ3 / H3 (Agent robustness):** Under identical source access and predeclared injected failures, does quality-aware tool selection / Retry / Replan / Abstain reduce the rate of **recommendations without sufficient evidence** versus a fixed Pipeline? Include latency, abstention rate and coverage so simply abstaining on every request cannot be counted as success.

These are hypotheses awaiting formal experiments. Targets such as MAE improvement ≥5%, Top-3 success +5 percentage points, full-occupancy recall ≥0.80 and p95 response ≤3 s are **preliminary go/no-go targets**, not observed effects.

## E. Proposed methodology

Historical JSONL and a planned real-time connector form the input, subject to schema, timestamp, spatial identity and capacity checks. Training and evaluation will use a chronological 60/20/20 division with group de-duplication, purge/embargo for overlapping future-label windows, features available only at time `t`, validation-only tuning and untouched final test evaluation. Persistence and same-weekday/time Historical Median are comparators to Random Forest and HistGradientBoosting; deep spatiotemporal models are not presumed superior.

For future-arrival outcomes, pair a user-arrival target with the **first legal observation inside a declared after-arrival window**; if absent, mark the label missing rather than impute success. For full occupancy classification, estimate event probabilities and evaluate PR-AUC, recall, Brier score and expected calibration error where the sample supports probabilistic modeling. A policy layer applies source freshness, candidate-specific quality, walking limits and domain rules to construct a Top-k evidence record. Against a fixed pipeline, controlled timeout/stale/schema-error injection will assess retry/replan/fallback behavior, evidence-less recommendation rates and response time.

## F. Proposed contributions and limitations

1. **Decision-centered problem definition:** align vacancy prediction and fullness risk with explicitly specified arrival horizon and operational constraints.
2. **Evidence-aware architecture:** specify a traceable quality gate and candidate-specific confidence/observation provenance with safe abstention rules.
3. **Comparative evaluation protocol:** jointly test prediction error, calibration, Top-k arrival success and Agent robustness against explicit baselines.
4. **Conservative deployment criteria:** report when data are too sparse or unreliable to support a trustworthy recommendation.

These are **intended contributions**, not empirically established achievements. The original proposal reports an exploratory New Taipei sample-notebook MAE near 7.12 parking spaces, but without the notebook, model, sample count, exact split or matched baselines in this GitHub repo, the number cannot establish performance superiority or operational feasibility. Full QA, hypothesis tests, calibrated risk and New Taipei GIS deployment remain **Planned / Unverified**.

## References cited

Bibliographic IDs and verification status: [`REFERENCE_AUDIT.md`](../references/REFERENCE_AUDIT.md). Related discussion: [`RELATED_WORK.md`](RELATED_WORK.md).

# Smart Parking Research Decomposition: A–F, 5 Mindsets, 3 Controversies, 10 Questions

> Scope: proposed New Taipei City **roadside segment** arrival-time risk. This is academic proposal analysis, **not a full experimental result**. Basis: original repository README snapshot; the user's teacher-assignment outline and proposal analysis. The actual DOCX/PPTX and standalone DESIGN.md are absent from GitHub, so detailed line-to-line verification against them remains blocked.

## A–F argument trace

| Stage | Research argument | Evidence state |
| --- | --- | --- |
| A — Attention Getter | 「現在有位」不保證「抵達時有位」，錯誤引導會增加時間與不確定風險 | Motivation; external background evidence not proof of this system |
| B — But / Gap | Observation age, spatial heterogeneity, changing demand, missing source and uncertain arrival horizon impede dependable advice | Research problem; claims of universality require literature scoping |
| C — Cure | Propose a risk-aware, quality-gated decision agent with justified Top-k candidates and abstention | Planned design |
| D — Development | Segment/time-aware historical JSONL, API connector, quality gate, past-only features, baseline/ML selection, risk rules, Retry/Replan/HITL, evidence log | Proposal architecture; implementation not verified in this repo |
| E — Experiments | Chronological 60/20/20 with purged windows; H1 baseline MAE/RMSE; H2 calibration and arrival-time Top-3; H3 injected API fault and abstention comparisons | Planned, unrun |
| F — Findings / limitation | The original proposal **reports** sample MAE ≈7.12 spaces; notebook, split, sample size and baseline results not available here. Full New Taipei conclusions remain unverified | Exploratory self-report only |

## Five core mindsets

1. **Quality precedes model complexity.** Validate schema, observation/fetch timestamps, duplicate keys, missingness and capacity bounds before fitting; compare usable-coverage and drift by segment.
2. **Prediction horizon must match arrival.** Define t (decision cutoff) and h (estimated arrival delay). Train/evaluate at t+h, report performance by horizon/segment; do not equate 10, 30 and 60 minutes.
3. **Preserve road-segment semantics.** Segment IDs, parking-space capacity, time zones, parking restrictions, location and source updates are domain variables; do not mix roadside observations with off-street lot status.
4. **Beat strong, fair baselines first.** Compare Persistence and same-weekday/time Historical Median under identical target, split, coverage and cutoff. Accept non-improvement as valid research evidence.
5. **Uncertainty belongs in decision policy.** Pair occupancy risk with data freshness, quality, calibration and abstention; report coverage–risk curves rather than optimizing error alone.

## Three controversies / trade-offs

1. **Simple statistical / tree models vs. deep spatiotemporal models.** More complexity may capture heterogeneity but increases resource/overfit risk. Decide based on horizon- and segment-stratified test performance plus inference cost.
2. **Pooled model vs. per-segment model.** Shared training increases samples but can mask local differences; segment-specific models may overfit sparse locations. Compare shared-with-segment-features, grouped regional, and per-segment where data allow.
3. **Point forecast vs. risk-sensitive recommendation.** Lowest MAE does not necessarily yield reliable Top-3 arrival decisions; probabilistic risk estimates bring calibration and selective prediction trade-offs. Evaluate Brier/ECE, top-k, coverage, walking distance and error under stale input.

## Ten deep questions and prospective tests

| # | Question | How to answer / falsifiable evidence |
|---|---|---|
| Q1 Why | Why is present availability insufficient? | Quantify occupancy changes between query t and arrival t+h. |
| Q2 Evidence | Does New Taipei JSONL support the intended horizons? | Full schema, segment coverage, sampling interval, label-availability audit. |
| Q3 What-if | What happens if API timeout or schema violation occurs? | Inject faults, measure retries, fallback and unsupported recommendation rate. |
| Q4 Trade-off | How much walking distance is worth risk reduction? | Predeclare utility weights, compare Pareto frontier and sensitivity. |
| Q5 Failure | How are wrong status codes, duplicates and impossible capacity handled? | Quality-gate tests with quarantined records and no fabricated zeros. |
| Q6 Comparison | Does an Agent improve outcomes over a fixed Pipeline? | Matched data/tools, fault-injection protocol, per-scenario coverage and risk. |
| Q7 Leakage | Can future arrivals or cross-boundary rolling windows leak labels? | Past-only feature checks; purged splits and repeated-label-group audit. |
| Q8 Transfer | Can Birmingham or Taichung results generalize to New Taipei? | No assumed transfer; compare schema, occupancy definition and distributions. |
| Q9 Ground truth | What counts as a successful arrival-time parking recommendation? | First valid observation in predeclared post-arrival tolerance; missing is unknown, not failure/success. |
| Q10 Decision | When should the Agent recommend, fallback, ask the user, or abstain? | Predeclare freshness, uncertainty and latency thresholds; report selective risk and abstention rate. |

## Status semantics

- **Implemented**: code or document shown in a verifiable artifact.
- **Evaluated**: direct execution results, methods and metrics can be inspected/reproduced.
- **Planned**: architecture, methods or metrics proposed but not demonstrated.
- **Blocked**: missing data or dependencies prevent completion.
- The repository README mentions an external original prototype and 9 successful tests: these are **proposal-reported**, not reproduced in this repository.

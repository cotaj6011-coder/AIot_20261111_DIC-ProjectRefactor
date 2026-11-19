# I. INTRODUCTION

**Working title:** *An Uncertainty-Aware AI Agent for Arrival-Time Parking Availability Prediction and Risk-Aware Recommendation*

**Scope:** This research proposal concerns New Taipei roadside parking arrival-time recommendation. New Taipei offline model evidence and Taichung's information-only Agent are reported separately in [Source Scope](../refactor/SOURCE_SCOPE_RECONCILIATION.md). Results from the source design are not independently reproduced in this repository.

## A. Motivation and setting

At the moment of a parking inquiry, an application may display vacant roadside spaces; nevertheless, those spaces can be occupied by the time a driver reaches a destination. This **query-to-arrival gap** matters when urban demand changes quickly, observations arrive late, or source quality is uneven. Accurate snapshot display alone therefore does not guarantee useful guidance. The study focuses on the availability of **New Taipei roadside segments at a user-specified arrival time**, not a claim that an existing deployed system already delivers such forecasts.

Established work includes broad surveys of urban parking prediction [5], spatiotemporal dynamic-graph forecasting of on-street availability [6], and multi-view curb-occupancy models [7]. A usable arrival-time decision workflow must also consider observation provenance, occupancy risk, practical walking constraints and a defensible way to decline recommendations when reliable inputs are absent.

SFpark provides a **direct external search-cost example**: reported search time in its pilot areas fell from **11 minutes 36 seconds to 6 minutes 36 seconds (43%)**, compared with **13%** in control areas, for weekdays 09:00–18:00 [S1]. This motivates measuring search-related decision usefulness. It does not measure New Taipei search time or isolate an AI effect: the program combined parking information, demand-responsive pricing and other management changes. Cao et al. [6] additionally examine how inaccurate predictive information can direct drivers toward already occupied spaces and extend searching. The project therefore asks whether arrival-time evidence can improve decisions, not whether an externally observed percentage can be transferred to this Agent.

## B. Problem definition

Let `t` denote the request/data cutoff and `h` the estimated travel-to-arrival horizon. For each eligible New Taipei roadside segment `s`, the intended response consists of an estimate of spaces available at `t+h`, a **calibrated full-occupancy probability only when supported by valid labels and calibration**, time/source/quality metadata and an explainable Top-k ranking. A recommendation must respect parking type, walking distance and other constraints.

Observations after `t` must not enter features or model selection at time `t`. Candidate-specific quality must govern the confidence assigned to that candidate. If the requested horizon is unsupported, the API is stale, or the source cannot be validated, the planner should fallback, request human confirmation or abstain, rather than silently convert unknown status to a vacancy.

This framing follows the original DOCX §1.2, §1.5 and the Agent/pseudocode in §4. It describes a **proposed New Taipei service**, not the Taichung current-information prototype.

## C. Research gap, with boundaries

Three gaps are relevant but must not be conflated:

1. **Project data-evidence gap:** The original proposal DOCX reports New Taipei JSONL availability and an early sample-notebook MAE of approximately 7.12 spaces. The project design also reports a large New Taipei offline comparison, but this repository does not contain the data or full technical reports to reproduce either. Therefore this gap concerns **verifiable evidence in this repository**, not the absence of New Taipei data in the world.
2. **Decision-evaluation gap:** Existing publications study prediction horizons, models, occupancy dynamics and uncertainty [5]–[11]. The **project-specific question** is whether forecasting quality and calibrated full-occupancy risk improve *arrival-time Top-k recommendations under walking constraints* beyond straightforward distance and persistence baselines.
3. **Agent-failure gap:** The proposed integration of source selection, quality gates, bounded Retry/Replan, fallback and abstention requires comparison with a **fixed pipeline using the same tools**. Agent use alone is not a novel algorithm or an automatically demonstrated improvement. Digital-twin decision-support integration also exists in prior work [12].

The resulting contribution, if supported by empirical tests, would be an **auditable combination** of horizon-matched forecasting, freshness/uncertainty safeguards and failure-aware recommendations **in this application setting**, not a blanket first-in-literature claim.

## D. Concrete method and operational workflow

The proposed implementation has **three method groups**, matching [AGENT_WORKFLOW.md](AGENT_WORKFLOW.md). **Context and data acquisition:** a Planner selects HTTP JSON connectors or historical JSONL readers, followed by schema, timestamp, missingness and capacity checks. **Temporal prediction and risk analysis:** past-only lag/rolling features feed Persistence, same-weekday/time Historical Median, Random Forest or HistGradientBoosting; Isotonic/Platt scaling are proposed calibration candidates, and fullness probabilities require validated labels and calibration. **Decision and autonomous orchestration:** explicit parking/walking constraints precede distance, calibrated-fullness-risk and candidate-quality ranking; a Tool Registry and Planner coordinate bounded retry, replanning, evidence logging and abstention. GIS presentation is concretely identified as React/TypeScript/Leaflet with FastAPI, following the **separate source-reported Taichung prototype** in DESIGN.md §§12–13; this is not evidence of a completed New Taipei integration. Haversine distance is an estimate, not a routed walking distance.

The operational sequence, failure branches and tool responsibilities are defined in [AGENT_WORKFLOW.md](AGENT_WORKFLOW.md). The proposed Agent automatically collects data, analyzes evidence and takes recommendation/replanning actions; the interface displays the resulting decisions. Its advantage over a fixed pipeline remains subject to H3 testing.

## E. Research questions and hypotheses

**H1 — Prediction superiority.** Under matched +30/+60-minute forecasting targets, and a leakage-controlled chronological split, do Random Forest or HistGradientBoosting features improve MAE by the prespecified minimum over Persistence? The `DESIGN.md` §10 **reports the opposite on aggregate New Taipei offline test rows** (Persistence MAE 0.326757 versus RF 0.402669, HistGB 0.537539; same 9,178,935 test rows). This **does not support H1's superiority claim on the source-reported aggregate comparison**; H1 must not be called validated or passed. The dataset/run is not independently reproduced in this repository. Horizon/segment/subgroup results should be examined without cherry-picking.

**H2 — User-oriented ranking.** Can risk-aware Top-3 selection increase the probability that at least one recommended segment is non-full at arrival, compared with distance-only ranking **at matched walking distance and accepted-request coverage**? Use a prespecified arrival-ground-truth tolerance, calibrated-risk diagnostics, Brier/ECE/PR-AUC, selective coverage and abstention measures. **Not evaluated here.**

**H3 — Failure-aware planning.** With identical source access and fault cases (timeout, stale observations, schema errors), does a quality-aware Agent reduce recommendations lacking adequate evidence relative to a fixed pipeline, while maintaining meaningful coverage and reasonable latency? Compare conditional error rate, number of supported recommendations, abstention and p95 latency. **Not evaluated here.**

## F. Source-reported stages versus proposed tests

| Stage | City / unit | Source says | What this repository can verify |
| --- | --- | --- | --- |
| Original proposal sample | New Taipei / preliminary notebook | Approximately 7.12-space MAE; 30-minute time features without segment ID (§5.1 DOCX) | Original claim preserved; notebook and split not present |
| Later Phase 2 offline | New Taipei roadside segment / +30 and +60 min | Persistence 0.326757, RF 0.402669, HistGB 0.537539 MAE; 9,178,935 common test observations (§10 DESIGN.md) | Textual source exists, but no independent rerun |
| Phase 2.5 credibility | New Taipei offline | Nominal boundary target crossing, substantial unchanged-occupancy fraction, conditional evaluation (§11 DESIGN.md) | Reported limitations preserved; corrected purged-split test not included |
| Phase 3–4.6 | Taichung current-information Agent | Source-specific snapshot tools, quality gates, GIS, scheduling; future predictions **DISABLED** (§§12–15 DESIGN.md) | DESIGN.md report only; runtime source/reproducible checks absent |
| Proposed H2/H3 | New Taipei arrival-time recommendation / fault injection | Planned in DOCX §6 | No matched arrival-outcome or Agent-vs-pipeline test |

Evaluation **will** use a chronological 60/20/20 scheme with **purging of training/validation examples whose target timestamps cross split boundaries**; a simple split on feature rows alone is insufficient because the later design acknowledges this exact issue. Any probability calibration must fit on a separate validation/calibration partition without using test outcomes. Test results must state the number of segments, accepted cases, horizons, missing-label exclusions and historical interval coverage.

Performance goals (MAE improvement ≥5%, full-recall ≥0.80, Top-3 success improvement ≥5 percentage points, p95 latency ≤3 s) in original DOCX §6.6 are **prospective go/no-go targets**, not achieved findings. If Persistence remains best, a scientifically valid outcome is to select it and report H1 as unsupported on the given evaluation.

## G. Intended contributions and limitations

1. An operational definition of roadside **arrival-time decision usefulness**, aligned with target times and parking constraints.
2. A planned evidence-aware recommendation contract tracking source freshness, candidate quality, risk representation and explicit abstention.
3. A falsifiable comparison of Persistence, statistical historical methods, candidate ML models and a fixed pipeline versus an Agent under matched conditions.
4. Transparent go/no-go reporting to avoid deploying a less reliable risk predictor simply because it is more complex.

**Scope limitation:** New Taipei predictive Top-k Agent remains a proposal. Taichung's information-oriented Agent work is a separate reported implementation with future predictions disabled. Do not infer New Taipei deployment, transferability, or real-world Top-3 outcomes from Taichung, Birmingham, SFpark or sample/notebook results.

## References

Numeric references [5]–[13] preserve the original DOCX numbering; [S1] is supplemental external-case evidence. Bibliographic verification and direct publisher links are in [REFERENCE_AUDIT.md](../references/REFERENCE_AUDIT.md).

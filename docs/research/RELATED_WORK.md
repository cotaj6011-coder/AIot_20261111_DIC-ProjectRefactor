# II. RELATED WORK

**Source basis:** Original proposal DOCX §2.1–§2.2 and references [5]–[13], with [DESIGN.md](../../DESIGN.md) for research-stage context. The nine original references are preserved in the comparison below.

## A. Domain knowledge and forecasting baselines

The survey by Ma, Huang and Li [5] categorizes urban parking prediction tasks and compares statistical, machine learning and deep learning families. It supports a problem-first model-selection strategy: occupancy of a roadside segment, time to arrival and availability of valid labels must be established before a more complex architecture is justified. It cannot validate a model on New Taipei by itself.

Schneble and Kauermann [8] study **individual on-street parking-spot occupancy durations** using time-to-event and semi-Markov modeling with Melbourne observations. Their domain and treatment of time-in-state may inform an occupancy-transition perspective, but an individual-spot duration outcome is not the same as a New Taipei segment's +30/+60-minute **available-space count**. The study is relevant precisely because it highlights a methodological contrast, not because its metrics can be directly reused here.

These sources strengthen the case for Persistence and same-weekday/time Historical Median as essential local benchmarks rather than weak competitors chosen only to make a neural model look good.

## B. Spatiotemporal and cross-region models

Cao, Chen and Wang [6] present an attention-based dynamic graph model for **on-street parking availability**, combining different graph representations with external information. Qian *et al.* [7] address **curb parking occupancy** through multi-view graph attention and recurrent fusion using geography, accessibility and POI signals. These works demonstrate that spatial interactions and domain context are already established research themes; the project cannot claim they are novel in general.

Vakrinou, Mantouka and Vlahogianni [9] study **four off-street garages in Athens** using multi-source input. Their findings distinguish favorable short- versus longer-horizon sequence architectures; however, garage counts, data ownership and access patterns do **not** translate automatically to road-segment outcomes. The original DOCX correctly excludes off-street integration from the first New Taipei validation scope. Likewise, Kuang *et al.* [10] apply deep meta-learning to heterogeneous regional parking prediction, which is a plausible later transfer-learning comparator but not evidence of New Taipei transfer without explicit domain shift tests.

## C. Uncertainty, source quality and selective decision-making

Nezhadettehad *et al.* [11] propose Bayesian neural networks that **explicitly address epistemic and aleatoric uncertainty** for parking prediction and investigate noisy/sparse-data and confidence-threshold conditions. This directly contradicts any broad statement that the parking literature has never modeled uncertainty. The proposed system's observation **freshness, missing-source quality, model variability and post-hoc calibration** are operational risk indicators; they should not be called a validated Bayesian decomposition. Whether a quality-aware abstention policy improves actual *arrival-time Top-k decision risk* must be independently tested.

The distinction matters: a lower mean regression error cannot alone establish well-calibrated full-occupancy probability or reliable decisions under sensor/API failure.

## D. Integrated urban decision-support systems and datasets

Piccialli *et al.* [12] present a digital-twin framework for urban parking management and mobility forecasting in **Caserta**, with multiple heterogeneous IoT/operational inputs and a prediction/simulation pipeline. This establishes that integrated parking and decision support are **not inherently novel**. A defensible project contribution is a bounded comparison of **arrival-time curb availability, candidate-specific evidence and explicit fault-handling** rather than a general claim of first integration.

The UCI Parking Birmingham dataset [13] is a public **off-street facility** dataset with 35,717 rows and four columns. It has legitimate value for quality-analysis methods but does not substitute for New Taipei roadside observations. Source `DESIGN.md` reports that a later New Taipei Phase 2 offline comparison was conducted and Persistence performed best in aggregate; this observation should be disclosed, not silently overwritten by the original proposal's H1 expectation.

## E. Complete source-aligned comparison (DOCX refs [5]–[13])

| Ref | Verified study / dataset | Method and data | What this project may learn | Non-transferable boundary |
| --- | --- | --- | --- | --- |
| [5] | Ma, Huang & Li (2024) | Urban parking prediction literature review | Choose target/horizon/data first; compare simple-to-complex methods | Review, not New Taipei evaluation |
| [6] | Cao, Chen & Wang (2025) | On-street dynamic attention graphs | Spatial and temporal interaction features | Requires dependable neighboring information and leakage control |
| [7] | Qian *et al.* (2025) | Curb occupancy MGA-GRU, multi-view spatial features | Accessibility/POI and spatial fusion may be useful | Domain features and external signals unvalidated for New Taipei |
| [8] | Schneble & Kauermann (2025) | Melbourne spot-level time-to-event/semi-Markov | Occupancy-duration state information | Spot duration differs from segment space count |
| [9] | Vakrinou, Mantouka & Vlahogianni (2026 volume) | Athens **off-street** garages, LSTM/Transformer and SHAP | Horizon and external-data trade-offs | Garage-to-curb transfer unsupported |
| [10] | Kuang *et al.* (2025) | Regional parking meta-learning with heterogeneous inputs | Potential cross-region adaptation research | New Taipei benefit not demonstrated |
| [11] | Nezhadettehad *et al.* (2025) | Parking BNN uncertainty and confidence thresholds | Selective prediction, uncertainty-aware decisions | Quality/freshness proxy ≠ validated uncertainty decomposition |
| [12] | Piccialli *et al.* (2025) | Caserta multi-source digital twin and forecasting | Integration plus operational context | No demonstration of this specific arrival-time Agent |
| [13] | Stolfi (UCI cited 2017) | Birmingham parking-garage observations (donated 2019) | QA and irregular sampling tests | Geographic/roadside and modern transportability limits |

**External policy example, not part of original DOCX [5]–[13]:** SFMTA SFpark evaluation [S1] describes benefits of parking availability/pricing operations. It does not establish any result for this project or isolate an AI Agent's effect.

## F. Research positioning and remaining evidence gap

Taken together, [5]–[12] cover forecasting, statistics, deep spatial models, uncertainty and integrated decision support. Therefore the research question is a **context-specific, testable systems comparison**, not that such categories do not exist in the literature. The proposed contribution is to evaluate whether a New Taipei **roadside arrival-time** workflow that combines data-quality gating, well-defined horizons, matched baselines, risk/coverage calibration and failure-aware Agent behavior generates better supported Top-k choices **than simpler alternatives using the same inputs**.

The answer remains uncertain: `DESIGN.md` §10 reports Persistence outperforming RF and HistGB in aggregate offline MAE, and §11 notes substantial no-change cases and label-boundary caveats. H2/H3 and live New Taipei Agent evidence remain missing from this GitHub repository.

For full citation metadata, audit levels and publisher/database URLs see [Reference Audit](../references/REFERENCE_AUDIT.md).
# II. RELATED WORK — Critical Comparative Synthesis

> This section balances domain parking studies and AI methods. It does not infer a universal research gap merely from a small selected bibliography. The full original nine-paper table mentioned in proposal-analysis materials was not present in this repository; this is a **verified core subset**, not a claimed reconstruction of all nine original entries.

## A. Parking prediction as a domain and modeling problem

Ma, Huang and Li's survey [R1] organizes parking research into behavioral, demand and parking-space prediction and synthesizes statistical, machine-learning and deep-learning approaches. It highlights spatiotemporal features and the challenge of noise or incomplete data. Its value here is to establish that prediction accuracy depends on observation quality, parking context and temporal/spatial structure; a survey does not establish the superiority of any specific New Taipei model.

For roadside occupancy, an attention-based dynamic graph study [R2] models multiple spatial relationships, while Qian *et al.* [R3] present a graph-attention/gated network with multi-view information for curb occupancy prediction. These studies motivate segment and neighborhood interactions and provide stronger research comparators than generic regression alone. Their existence also limits novelty claims: spatial graph forecasting is an established research direction. This proposal instead prioritizes reproducible baseline comparison and decision usefulness at arrival under the available New Taipei data.

## B. Uncertainty, reliability and selective prediction

Nezhadettehad *et al.* [R4] explicitly investigate Bayesian neural-network parking prediction and selective decisions using confidence thresholds under data scarcity and artificial noise. This is important counterevidence to any blanket statement that parking research lacks uncertainty quantification. However, calibrated prediction, explicit epistemic/aleatoric modeling and source freshness are **not interchangeable**. The proposed system's primary mechanism is a quality-aware and potentially calibrated **decision policy**; it does not claim to implement or validate Bayesian uncertainty decomposition.

A credible comparison should include not only predictive error but also selective risk at a stated coverage, the false reassurance caused by stale observations, and whether the system abstains when it cannot justify candidate ordering. Such tests are an **unverified research plan**, not a demonstrated difference from [R4].

## C. Operational parking data and system context

SFpark [R7] couples better parking information with **demand-responsive pricing and management** and documented improved search-related outcomes. Its evaluation is an urban parking management case, not an Agent or arrival-time forecasting benchmark. Its reported reductions therefore support the importance of parking service design, but they cannot be credited to our proposed approach.

The UCI Parking Birmingham dataset [R6] can support methodological exploration and QA prototypes, but its geographic, temporal and target semantics cannot be assumed to match New Taipei curbside segments. The original README states a separate Birmingham QA prototype and a sample New Taipei notebook, neither of which is present here as reproducible code.

## D. Comparison matrix

| Source | Domain / method | Relevant contribution | Boundary for this project | Identifier status |
| --- | --- | --- | --- | --- |
| [R1] Ma et al., 2024 | Urban parking prediction review | Model taxonomy, spatiotemporal challenges | Survey, not a New Taipei or fault-tolerant Agent test | DOI externally checked |
| [R2] *An attention-based dynamic graph model…*, 2025 | On-street parking, attention/dynamic graphs | Spatial dependence and external features | Does not by itself validate our failure-aware Top-k policy | DOI/title checked; author list pending |
| [R3] Qian et al., 2025 | Curb occupancy, graph-attention gated units | Spatial/multi-view curb prediction | Graph prediction result is not arrival-time decision utility | DOI/title/author checked |
| [R4] Nezhadettehad et al., 2025 | Bayesian uncertainty-aware parking prediction | Uncertainty and selective prediction under limited/noisy data | Different uncertainty formulation; avoid claiming field lacks uncertainty work | DOI/full text checked |
| [R5] Schneble and Kauermann, 2025 | On-street occupancy statistical modeling | Statistical comparator to complex AI | DOI currently unverified independently; no numeric claim used | PENDING |
| [R6] UCI Parking Birmingham | Public dataset | External QA and prototyping | Different city/target; cannot transfer performance estimates | PENDING dataset-page check |
| [R7] SFMTA SFpark evaluation | Real-world parking management with demand-responsive pricing | Practical policy/service value | Not an evaluation of this AI Agent or model | Official SFMTA checked |

## E. Bounded project research gap

Based on [R1–R4] and the supplied proposal, the **testable contribution sought here** is not an original forecasting family but evaluation of an integrated **New Taipei roadside, arrival-time, evidence-aware decision workflow** with: (i) observed data quality and freshness checks; (ii) predictions matched to arrival horizons and compared against persistence; (iii) calibrated occupancy risk and route-constrained Top-k; and (iv) fault-triggered retry/replanning/fallback/abstention with logs.

It remains an *open empirical question* whether this composite workflow improves a fixed pipeline or simpler ranking. A systematic claim about the entire literature would require a defined search protocol and larger evidence set.

## F. Research questions to preserve in future work

- What is the benefit over Persistence at 10/30/60-minute horizons for segments with reliable labels?
- How do uncertainty rejection and freshness thresholds affect risk **and** usable coverage?
- When sources fail, does dynamic Agent planning improve supported recommendations relative to a fixed pipeline using the same tools?
- Does improved full-occupancy risk estimation produce better Top-3 arrival-time outcomes at comparable walking distance?

The bibliography and verified source URLs are maintained separately in [Reference Audit](../references/REFERENCE_AUDIT.md).

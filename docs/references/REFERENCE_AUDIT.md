# Reference and Evidence Audit

Audit performed as a **limited, targeted external DOI / publisher check**, supplemented by original repository claims. It is not a systematic literature search. Title verification is not proof of all claims in a full text. Accessed during the November 2026 document refactor.

## External sources

| ID | Source | Evidence checked | Audit |
| --- | --- | --- | --- |
| R1 | Ma, C., Huang, X., Li, J., “A review of research on urban parking prediction,” *Journal of Traffic and Transportation Engineering (English Edition)* 11(4), 700–720, 2024. https://doi.org/10.1016/j.jtte.2023.11.004 | Publisher page confirms authors/title/2024 review, spatiotemporal and noise themes | **VERIFIED metadata + abstract** |
| R2 | “An attention-based dynamic graph model for on-street parking availability prediction,” *Transportation Research Part A*, vol. 193, art. 104391, 2025. https://doi.org/10.1016/j.tra.2025.104391 | Publisher page confirms title, year, graph methods; author list not copied without independent inspection | **VERIFIED title/DOI; author list PENDING** |
| R3 | Qian, C., Yang, K., He, J., Peng, X., Huang, H., “Curb parking occupancy prediction based on real-time fusion of multi-view spatial-temporal information using graph attention gated networks,” *Applied Soft Computing*, vol. 171, 112781, 2025. https://doi.org/10.1016/j.asoc.2025.112781 | Publisher preview confirms title/authors, method, date | **VERIFIED metadata + summary** |
| R4 | Nezhadettehad, A., Zaslavsky, A., Rakib, A., Loke, S.W., “Uncertainty-Aware Parking Prediction Using Bayesian Neural Networks,” *Sensors*, 25(11), 3463, 2025. https://doi.org/10.3390/s25113463 | Publisher full text confirms uncertainty and abstention/selective confidence setting | **VERIFIED metadata + research scope** |
| R5 | Schneble, M., Kauermann, G., “Statistical modelling of on-street parking spot occupancy in smart cities,” 2025. https://doi.org/10.1093/jrsssc/qlaf017 | DOI appeared in original README; direct independent source could not be accessed in this check | **PENDING metadata/full text** |
| R6 | Stolfi, D., “Parking Birmingham,” UCI Machine Learning Repository. https://doi.org/10.24432/C51K5Z | Dataset appears in original README; direct independent access unsuccessful in this check | **PENDING metadata/target semantics** |
| R7 | San Francisco Municipal Transportation Agency, SFpark Pilot Project Evaluation / 2014 public summary. https://www.sfmta.com/getting-around/drive-park/demand-responsive-pricing/sfpark-evaluation and https://www.sfmta.com/press-releases/sfpark-evaluation-shows-parking-easier-cheaper-pilot-areas | Official SFMTA summary reports 43% reduction in parking search time and 30% reductions in circling-related VMT/GHG for pilot areas | **VERIFIED external historical policy evidence; NOT this Agent's results** |

## Critical caveats

- **SFpark attribution**: Its intervention combines real-time information, demand-responsive pricing and other parking management changes. It does not isolate or demonstrate effects of this proposed AI Agent. Even controlled pilot analysis is not evidence of a causal effect for New Taipei deployment.
- **Novelty**: R2/R3 already study predictive parking spatiotemporal methods and R4 studies uncertainty-aware prediction. Do not claim the field has no such methods.
- **R5/R6**: The supplied links alone are not an independently audited citation. Keep flagged pending, or verify when accessible.
- **Original nine-paper comparison**: The user's proposal analysis PDF reports nine papers in the original document, but the entire source bibliography is not present in this repository. We have **not** invented two missing papers or claimed to reproduce the original table.
- **New Taipei JSONL / 7.12 MAE**: Dataset inventory, notebook, pipeline and reproducible samples are absent from this GitHub repo; both are proposal-reported and remain **unverified here**.
- **Historical scope**: The README dates 2025-05-01 to 2026-11-02; segment identifiers, time zones, sampling intervals and source licensing remain to be audited from raw metadata.
- **Agent prototype**: “9 tests OK” and prototype implementation claims in README cannot be verified without test code/output in this repository.

## Evidence type matrix

| Claim | Evidence type | Status |
| --- | --- | --- |
| This repository includes documented OpenSpec change artifacts | GitHub paths/commit history | Verifiable after commit |
| Refactored Intro, Related Work and 5/3/10 exist | GitHub text artifact | Verifiable after commit |
| New Taipei predictive model is better than Persistence | Held-out experimental evidence | **NOT EVALUATED** |
| Top-3 risk ranking has better arrival success | Held-out recommendation experiment | **NOT EVALUATED** |
| Agent retry/replan reduces unsupported suggestions | Matched fault-injection tests | **NOT EVALUATED** |
| Sample MAE ≈7.12 | Source README assertion, notebook absent | **REPORTED, NOT REPRODUCED** |
| Official SFpark 43% / 30% outcomes | SFMTA policy/evaluation evidence | **EXTERNAL, NOT PROJECT OUTCOME** |

## Sources links reviewed

- https://www.sciencedirect.com/science/article/pii/S2095756424000710
- https://www.sciencedirect.com/science/article/abs/pii/S0965856425000199
- https://www.sciencedirect.com/science/article/pii/S1568494625000924
- https://www.mdpi.com/1424-8220/25/11/3463
- https://www.sfmta.com/getting-around/drive-park/demand-responsive-pricing/sfpark-evaluation
- https://www.sfmta.com/press-releases/sfpark-evaluation-shows-parking-easier-cheaper-pilot-areas

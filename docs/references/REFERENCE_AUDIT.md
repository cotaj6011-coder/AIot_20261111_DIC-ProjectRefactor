# Reference Audit — Original DOCX [5]–[13]

**Basis:** Original `docs/submission/智慧停車AI_Agent_Proposal_新北市(1).docx` p.10–11 References, pp.4–5 Article Summary. All nine references below were individually checked against publicly accessible publisher or dataset landing pages for this bibliography audit. Audit of **metadata and abstract/preview claims** is distinct from independent replication of paper results, and restricted/full papers are not asserted to have been read in full.

## Original nine sources (numbering preserved)

| DOCX | Source (publisher bibliographic record) | Verification and supported topic | Limitations |
| --- | --- | --- | --- |
| **[5]** | **C. Ma, X. Huang, J. Li**, “A review of research on urban parking prediction,” *Journal of Traffic and Transportation Engineering (English Edition)* **11**(4), 700–720 (2024). https://doi.org/10.1016/j.jtte.2023.11.004 | **PASS metadata / abstract**: review of prediction approaches and research directions; [Publisher](https://www.sciencedirect.com/science/article/pii/S2095756424000710) | Review is not a New Taipei experiment. |
| **[6]** | **R. Cao, H. Chen, D. Z. W. Wang**, “An attention-based dynamic graph model for on-street parking availability prediction,” *Transportation Research Part A* **193**, 104391 (2025). https://doi.org/10.1016/j.tra.2025.104391 | **PASS metadata / abstract; 2026-11-19 publisher-preview recheck**: static/dynamic/hidden graph forecasting plus simulation of inaccurate predictive information extending parking search; [Publisher preview](https://www.sciencedirect.com/science/article/abs/pii/S0965856425000199) | No claim of this project's performance advantage. |
| **[7]** | **C. Qian, K. Yang, J. He, X. Peng, H. Huang**, “Curb parking occupancy prediction based on real-time fusion of multi-view spatial-temporal information using graph attention gated networks,” *Applied Soft Computing* **171**, 112781 (2025). https://doi.org/10.1016/j.asoc.2025.112781 | **PASS metadata / abstract**: curb multi-view graph-attention recurrent fusion; [Publisher](https://www.sciencedirect.com/science/article/pii/S1568494625000924) | Effects in paper cannot be imported as New Taipei results. |
| **[8]** | **M. Schneble, G. Kauermann**, “Statistical modelling of on-street parking spot occupancy in smart cities,” *Journal of the Royal Statistical Society Series C* **74**(4), 1128–1149 (2025). https://doi.org/10.1093/jrsssc/qlaf017 | **PASS metadata / abstract**: time-to-event / semi-Markov modeling of Melbourne on-street spot occupancy; [Publisher](https://academic.oup.com/jrsssc/article/74/4/1128/8046921) | Spot-level duration ≠ segment-level available-space count. |
| **[9]** | **K. Vakrinou, E. G. Mantouka, E. I. Vlahogianni**, “Leveraging multisource data for off-street parking occupancy prediction: a twofold analysis,” *International Journal of Transportation Science and Technology* **21**, 352–371 (2026; DOI registered 2025). https://doi.org/10.1016/j.ijtst.2025.02.005 | **PASS DOI / title / venue / volume / abstract**: Athens four-garage off-street occupancy, LSTM/Transformer, horizon dependence and SHAP; [Publisher](https://www.sciencedirect.com/science/article/pii/S204604302500036X) | Off-street results and small facility count; cannot claim road-segment validity. |
| **[10]** | **H. Kuang, K. Deng, Q. Wang, W. Ye, H. Qu, J. Li**, “Deep meta-learning approach for regional parking occupancy prediction considering heterogeneous and real-time information,” *Advanced Engineering Informatics* **64**, 102969 (2025). https://doi.org/10.1016/j.aei.2024.102969 | **PASS metadata / abstract**: regional heterogeneous real-time information and deep meta-learning; [Publisher](https://www.sciencedirect.com/science/article/pii/S1474034624006207) | Transfer to New Taipei untested here. |
| **[11]** | **A. Nezhadettehad, A. Zaslavsky, A. Rakib, S. W. Loke**, “Uncertainty-Aware Parking Prediction Using Bayesian Neural Networks,” *Sensors* **25**(11), 3463 (2025). https://doi.org/10.3390/s25113463 | **PASS metadata / open full text abstract and method claims**: BNN addresses epistemic and aleatoric uncertainty, data scarcity/noise and confidence-based selection; [Publisher](https://www.mdpi.com/1424-8220/25/11/3463) | Distinguish proposed project's freshness/quality proxy from BNN decomposition. |
| **[12]** | **F. Piccialli, S. Amitrano, D. Cerciello, A. Borrelli, E. Prezioso, M. Canzaniello**, “A digital twin framework for urban parking management and mobility forecasting,” *Nature Communications* **16**, 9400 (2025). https://doi.org/10.1038/s41467-025-65306-w | **PASS publisher metadata / full-text overview**: Caserta digital twin, multi-source parking management/forecasting and simulation; [Publisher](https://www.nature.com/articles/s41467-025-65306-w) | Integrated parking decision support is existing prior work; no novelty claim of first integration. |
| **[13]** | **D. Stolfi**, “Parking Birmingham,” *UCI Machine Learning Repository*, cited as 2017 dataset, repository donation 2019. https://doi.org/10.24432/C51K5Z | **PASS metadata / dataset description**: 35,717 observations, four columns, October–December 2016, off-street garages; [UCI](https://archive.ics.uci.edu/dataset/482/parking+birmingham) | Repository says missing values exist; a particular local CSV's 0 blank cells is a separate source-specific QA claim. |

**Source alignment:** Original DOCX Reference labels [1]–[4] are **data, local schema, local sample notebook, and planned API**, not peer-reviewed literature. Their source/availability is preserved but **not independently verified** by checking the nine publication DOI records above.

## Supplemental outside-case evidence (NOT part of original [5]–[13])

**[S1]** SFMTA, *SFpark Pilot Project Evaluation Summary* (2014), printed pp. 12–13 (PDF page 7). [Official evaluation page](https://www.sfmta.com/getting-around/drive-park/demand-responsive-pricing/sfpark-evaluation), [Official summary PDF](https://www.sfmta.com/media/11985/download?inline=). **Rechecked 2026-11-19 against the official summary:**

| Quantity | Pilot | Control | Interpretation |
| --- | --- | --- | --- |
| Reported parking-search time, weekdays 09:00–18:00 | 11:36 → 6:36; **−5 min / −43%** | 6:24 → 5:36; **−13%** | Direct external evidence of search cost; percentages are within-area before/after changes, not an isolated AI treatment effect. |
| Circling-related vehicle miles per day | 8,134 → 5,721; **−30%** | 3,110 → 2,933; **−6%** | External parking-management outcome; not this Agent's result. |
| Search-related greenhouse gases, metric tons per day | 7.0 → 4.9; **−30%** | 2.7 → 2.5; **−6%** | Rounded official figures; not all citywide transport emissions. |

SFpark combined information, demand-responsive pricing and other parking-management changes. The short abstract and infographic use the search-time figures for motivation; they **do not establish New Taipei baseline search time, a future Agent improvement target, or causal attribution to one component**. The 2014 case is identified as historical evidence, not presented as a new 2026 study.

**[6] Direct problem-link check (2026-11-19):** The publisher abstract and section preview describe simulation of prediction accuracy and parking searching; the preview explains that erroneous information can send a driver to an occupied space and prolong search. This supports the A→B link between search cost and unreliable arrival decisions. Only the accessible abstract/preview was checked; a full-text replication is not claimed. No effect size from this paper is imported into the project.

## Project claims versus citations

| Claim | Artifact | Evidence state | Correct wording |
| --- | --- | --- | --- |
| Early New Taipei notebook MAE ≈ 7.12 spaces | Original DOCX §5.1 and README | **SOURCE-REPORTED / NOT REPRODUCED** | Exploratory sample result; no matched split/capacity/baseline evidence here. |
| New Taipei Phase 2 Persistence MAE 0.326757 (RF 0.402669; HistGB 0.537539) | DESIGN.md §10 | **SOURCE-REPORTED EVALUATED ELSEWHERE; NOT REPRODUCED HERE** | Offline +30/+60 comparison across same 9,178,935 test rows as reported; cannot claim production model readiness. |
| Temporal crossing around split boundaries | DESIGN.md §11 | **SOURCE-REPORTED LIMITATION** | Nominal split boundary target crossing requires purged-label revalidation. |
| Taichung information-only Agent | DESIGN.md §§12–15 | **SOURCE-REPORTED IMPLEMENTED ELSEWHERE** | Current-information Agent/GIS with prediction DISABLED; executable code not present here. |
| New Taipei H2/H3, calibration, Top-3 user benefit | Original DOCX §6 and newer academic drafts | **PLANNED / NOT RUN IN REPOSITORY** | Testable hypotheses, no demonstrated superiority. |

## Scope and verification protocol

1. **Bibliography PASS** means that the title, author(s), DOI, venue/year, and **described research theme** were checked on publisher/dataset pages. It does **not** mean every experiment, figure, statistical conclusion or cited result was reproduced.
2. Existing claims about API schema/license, field-level occupancy codes, original project test results and raw dataset quantities are **source assertions**, not data audits performed by the GitHub connector.
3. Specific DOI records verified above come from current publisher / official data site pages. The formal LMS marking scheme and grading thresholds cannot be verified from these publications.
4. SFpark external outcomes are contextual evidence only.


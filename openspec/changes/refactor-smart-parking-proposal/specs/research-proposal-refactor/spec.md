# Research Proposal Refactor — Delta Specification

## REQ-01 Preserve source provenance
The refactor MUST retain a byte-for-byte textual snapshot of the starting repository README, identify the base commit, and distinguish source text from later authored revisions.

### Scenario: reviewer checks revision origin
**Given** only the initial GitHub README is present, **when** the revision is submitted, **then** the reviewer can locate `docs/baseline/README_BEFORE.md` and a change map identifying old sections, new sections, and unverifiable missing sources.

## REQ-02 A–F academic argument
The proposal MUST explicitly cover A Attention Getter, B But/Gap, C Cure, D Development, E Experiments, and F Findings/limitations. F MUST not imply planned experiments were completed.

### Scenario: abstract inspection
**When** a reviewer reads the abstracts and A–F mapping, **then** all six elements are identifiable, preliminary metrics are labeled exploratory, and future experiments use future-tense language.

## REQ-03 Deep research 5/3/10
The artifact MUST contain exactly five core mindsets, three controversies/trade-offs and ten deep questions, with evidence or testable implications for each.

### Scenario: count and relevance
**When** a reviewer inspects `docs/research/RESEARCH_5_3_10.md`, **then** every numbered item maps to the arrival-time parking problem and proposed evaluation.

## REQ-04 Introduction
The revised Introduction MUST state motivation, operational unit (New Taipei roadside segments), arrival-horizon problem, current technical limitations, agent necessity, falsifiable H1–H3 and proposed contributions; it MUST separate source-supported evidence from proposed hypotheses.

### Scenario: no false accomplishment
**When** the Introduction is read, **then** unverified New Taipei end-to-end system performance is not described as demonstrated.

## REQ-05 Related Work
Related Work MUST compare identifiable publications, their approaches, data/problem alignment, relevance and boundaries. It MUST NOT assert that no prior work studies uncertainty or arrival-horizon prediction when prior publications already do.

### Scenario: evidence gap
**When** claims of novelty are inspected, **then** they are phrased as a proposed *joint evaluation* of predictive quality, freshness, failure-aware decision-making and recommendation utility, not as unsubstantiated worldwide firsts.

## REQ-06 Reproducible evaluation plan
The proposal MUST define chronological 60/20/20, purge/embargo treatment when future targets or windows cross split boundaries, past-only features, baseline comparisons, classification calibration and recommendation evaluation without data leakage.

### Scenario: cutoff
**When** computing a forecast at time t for horizon h, **then** no input from after t is allowed and target/feature windows may not leak between train, validation and test.

## REQ-07 Evidence states and citations
All nontrivial results MUST carry evidence status (Implemented, Evaluated, Planned or Blocked), source city, dataset and horizon as applicable; external bibliographic entries MUST be traceable and unresolved claims explicitly marked.

### Scenario: reported MAE
**When** the value 7.12 parking spaces appears, **then** it is labelled as an exploratory New Taipei sample notebook claim; sample size, model, split, and baseline comparison are missing, and no feasibility superiority is inferred.

## REQ-08 Delivery and acceptance
The GitHub README MUST link all OpenSpec and revised-document artifacts, while acceptance MUST distinguish document content checks from an actual CLI validation or experimental run.

### Scenario: grader review
**When** the grader opens README, **then** the change, before/after, Intro, Related Work, 5/3/10 and acceptance evidence are discoverable without extra tooling.

## REQ-09 Submission boundaries
The repository MUST NOT imply the teacher required duplicating every LMS-uploaded PDF/PNG in GitHub. The record MUST flag formally unverified LMS submission rules.

### Scenario: attached images
**When** PDFs/PNGs are absent from GitHub, **then** the README distinguishes externally submitted class attachments from version-controlled refactor artifacts.

# Spec Delta — Research Proposal Refactor

## Purpose

This capability defines reviewable, evidence-grounded academic proposal deliverables for the DIC3 Smart Parking Agent refactor. The requirements govern document outputs and truthfulness, not execution of a deployed parking system.

## ADDED Requirements

### Requirement: Primary-source traceability
The refactor SHALL preserve the original DOCX, DESIGN.md, proposal-analysis PDF and pre-refactor README as separate source artifacts, and SHALL map changed academic sections to actual source headings.

#### Scenario: Reviewer checks revised sections
- **GIVEN** the repository contains both primary proposal and later design documents
- **WHEN** the reviewer opens the before/after audit
- **THEN** each revised Introduction/Related Work section maps to identifiable original DOCX section numbers
- **AND** the supplied DESIGN.md is not misrepresented as having been rewritten or available before the first change

### Requirement: A–F academic argument
The abstract artifact SHALL explicitly identify A Attention Getter, B Gap, C Cure, D Development, E Experiments and F Findings/limitations, while preserving distinctions between planned work and source-reported results.

#### Scenario: A–F abstract inspection
- **WHEN** a reviewer inspects the bilingual abstracts and argument map
- **THEN** all six concepts are identifiable
- **AND** the early 7.12-space sample and later 0.326757-space offline MAE are not treated as matched tests

### Requirement: Five-three-ten research analysis
The refactor SHALL contain five core mindsets, three trade-offs and ten deep questions grounded in arrival-time parking decision utility.

#### Scenario: Review analysis count
- **WHEN** the reviewer inspects the deep-research artifact
- **THEN** exactly five mindsets, three trade-offs and ten questions are enumerated
- **AND** questions connect to evidence, evaluation or failure handling

### Requirement: Academically bounded Introduction
The Introduction SHALL describe New Taipei roadside segment arrival-time research, clear problem formulation, bounded novelty, falsifiable H1–H3, methods, expected contributions and limitations.

#### Scenario: Evaluate source and city scope
- **WHEN** a reviewer reads the Introduction
- **THEN** New Taipei offline forecasting and Taichung current-information Agent implementation are distinguished
- **AND** a reported baseline advantage is not silently converted into a tree-model victory

### Requirement: Full source-aligned Related Work
The Related Work SHALL critically compare all nine scholarly/data references [5]–[13] in the original DOCX and preserve their geographic, target and method differences.

#### Scenario: Source table audit
- **WHEN** the reviewer reads the comparison table and reference audit
- **THEN** all original identifiers [5]–[13] appear with verifiable DOI or dataset landing page
- **AND** metadata verification is not misrepresented as experimental reproduction

### Requirement: Reproducible evaluation protocol
The documents SHALL specify time-cutoff-only features, chronological partitions, purging target windows crossing split boundaries, valid arrival-ground-truth tolerance and matched benchmark/Agent comparisons.

#### Scenario: Temporal label boundary
- **GIVEN** a sample at time t has a future target at t+h
- **WHEN** its target timestamp crosses a nominal train/validation or validation/test boundary
- **THEN** the evaluation protocol excludes or purges it rather than allowing cross-split target reuse
- **AND** all features are restricted to those available no later than t

### Requirement: Evidence-state precision
Each substantive system or performance claim SHALL distinguish source-reported implementation/evaluation from repository-verified artifacts, planned results and blocked reproduction.

#### Scenario: Two different MAE claims
- **WHEN** the documents report the 7.12-space notebook sample or the Phase 2 offline 0.326757/0.402669/0.537539 figures
- **THEN** their stages, data source, non-comparability and non-reproduction in this GitHub repository are stated
- **AND** H2/H3 and New Taipei live recommendation success are not labelled as tested

### Requirement: Honest OpenSpec validation status
The change SHALL provide proposal, delta spec, design, tasks and acceptance artifacts but SHALL report native CLI validation as NOT RUN when it has not actually been executed.

#### Scenario: Review change completeness
- **WHEN** a reviewer opens the README and acceptance report
- **THEN** all refactor artifacts have direct links and manual evidence statuses
- **AND** no claimed PASS includes native CLI or production-model execution evidence that was not obtained

### Requirement: Submission boundary clarity
The delivery documentation SHALL distinguish GitHub refactor artifacts from LMS-submitted files and SHALL not invent a teacher requirement to upload all media twice.

#### Scenario: PDF/PNG submission location
- **WHEN** the reviewer looks for the PDF or infographic
- **THEN** the PDF attachment in the repository is identified as an additional preserved source
- **AND** any separate LMS submission expectation remains unverified unless a formal requirement is available

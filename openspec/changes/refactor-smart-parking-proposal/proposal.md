# Change Proposal: Refactor Smart Parking AI Agent Research Proposal

## Why

The existing repository primarily contains a feature-oriented proposal README and OpenSpec Skills. The DIC3 assignment requires an auditable, specification-driven **document refactor** with an A–F abstract, 5 core mindsets, 3 controversies/trade-offs, 10 deep questions, and academically defensible Introduction and Related Work. Merely installing Skills does not meet this goal. The existing README has planned performance targets and exploratory sample results; these must not be represented as validated findings.

## What Changes

- Preserve the exact original README as `docs/baseline/README_BEFORE.md` and retain its existing root content.
- Create an explicit 5/3/10 evidence analysis and A–F abstract mapping.
- Produce research-style Introduction and Related Work, with a comparison table and source-level evidence status.
- Make H1–H3 falsifiable, distinguish New Taipei City data from Birmingham and other prototype experience, and specify data-quality and temporal-leakage controls.
- Include bilingual abstracts and a verified-or-pending bibliography.
- Record a reproducible before/after mapping, acceptance evidence, and any unresolved sources.
- Update README to direct graders to the OpenSpec artifacts and refactored documents.

## Non-goals

- No new prediction training, API deployment, GIS implementation, data fabrication, or claimed model validation.
- No automatic copy of PDFs/PNGs already submitted in the teaching platform.
- No claim of successful `openspec init` or `openspec validate` execution; the GitHub connector edits files but cannot execute CLI commands.

## Source of truth

1. Current repository README snapshot (committed verbatim).
2. The student's supplied assignment instructions and 2026-11-11 lecture transcript discussed in ChatGPT, including the A–F and 5/3/10 workflow.
3. The student's supplied Smart Parking proposal analysis PDF and bilingual abstract; their statements are treated as proposal claims unless independently reproduced or verified.
4. External papers linked in `docs/references/REFERENCE_AUDIT.md`.

**Source limitation:** The original DOCX/PPTX/standalone DESIGN.md and raw datasets are not present in this GitHub repository at the time of the change. Full diff against those artifacts is **BLOCKED** until available. This is not the same as the preserved README before/after comparison.

## Success criteria

- Specs each have testable scenarios and are linked to output files.
- A–F and 5/3/10 are explicitly documented and coherent.
- Introduction states problem, gap, research questions/hypotheses, contribution **as a proposal**.
- Related Work compares specific papers and states which gaps are proposed rather than proven.
- References have traceable identifiers, with unresolved entries explicitly flagged.
- No unsupported experimental, deployment, or CLI success claims.
- Acceptance summary reports PASS/PARTIAL/BLOCKED by evidence, rather than marking everything passed.

# Paper Topic Builder

Paper Topic Builder is a Codex Skill for generating evidence-based empirical paper topics from a Zotero literature collection. It is designed for management, entrepreneurship, organization studies, strategy, marketing, information systems, and related social science research.

The Skill does not invent topics from scratch. It reads a real Zotero Collection, subcollection, tag, saved search, or fallback bibliography/PDF corpus, extracts evidence from metadata, abstracts, full-text PDFs, notes, and annotations, then builds topic ideas that remain traceable to the literature base.

## Author

- Author: 视频号「扣子说AI」
- Purpose: help researchers convert Zotero literature collections into structured, evidence-grounded empirical research topics.

## What It Does

1. Reads the requested Zotero Collection, subcollection, tag, saved search, or item list first
2. Classifies each paper as quantitative, qualitative, mixed methods, theory, review, method, or meta-analysis
3. Extracts research topics, contexts, theories, findings, limitations, and future research directions
4. Identifies quantitative variable roles, including IVs, DVs, mediators, moderators, controls, hypotheses, results, and measurement sources
5. Extracts qualitative mechanisms, first-order concepts, second-order themes, aggregate dimensions, and boundary conditions
6. Synthesizes theory gaps, mechanism gaps, context gaps, method gaps, conflicting results, and variable-role gaps
7. Builds a variable network and identifies promising role repositioning opportunities
8. Recombines variables into antecedent-mechanism-outcome-boundary-condition models
9. Generates at least 10 empirical topic cards
10. Selects the top 3 research stories
11. Evaluates each topic from an SSCI-style management reviewer perspective

## Installation

Clone this repository into your Codex skills directory using the new Skill folder name:

```bash
git clone https://github.com/longkou1988/paper-topic-builder.git ~/.codex/skills/paper-topic-builder
```

Restart Codex. Then invoke the Skill with:

```text
$paper-topic-builder
```

If you installed an earlier local folder name, rename the folder to:

```text
~/.codex/skills/paper-topic-builder
```

## Usage

Basic example:

```text
Use $paper-topic-builder to analyze my Zotero Collection: entrepreneurship/female entrepreneurship
```

More focused example:

```text
Use $paper-topic-builder to analyze my Zotero Collection: female entrepreneurship. Focus on financing constraints, entrepreneurial resilience, institutional environment, digital platforms, and SSCI-ready empirical topic ideas.
```

Tag-based example:

```text
Use $paper-topic-builder to analyze my Zotero tag: digital entrepreneurship. Generate evidence-grounded empirical topic cards and reviewer evaluations.
```

## Zotero-First Policy

The Skill prioritizes the Zotero plugin in the active Codex environment. It should not ask the user to manually export `.bib` files or PDFs before attempting Zotero access.

Fallback inputs are used only when:

- the Zotero plugin is unavailable;
- the requested Collection, subcollection, tag, or item list cannot be resolved;
- metadata is too incomplete;
- PDF attachments are missing, inaccessible, unreadable, incomplete, or garbled;
- the user explicitly provides `.bib`, `.ris`, `.csv`, or a local PDF folder as an alternative source.

## Outputs

The Skill writes the following files under `output/`:

1. `literature_matrix.xlsx`
2. `variable_role_matrix.xlsx`
3. `qualitative_mechanism_matrix.xlsx`
4. `theory_gap_matrix.xlsx`
5. `variable_network_summary.md`
6. `topic_cards.md`
7. `model_candidates.md`
8. `final_research_story.md`
9. `reviewer_evaluation.md`

## Quality Rules

- Do not fabricate literature facts, DOI, journal names, theories, findings, variables, or model paths.
- Every substantive extraction must be traceable to Zotero metadata, abstract, PDF text, note, annotation, or fallback source file.
- If only the abstract is available, mark the analysis basis clearly.
- If full text is unavailable, mark the paper as full text unavailable and state the reason.
- Unsupported fields must be marked as insufficient evidence.
- Low-confidence judgments must be labeled.
- Variable roles require evidence sections, evidence text, and confidence levels.
- Topic ideas must explain why the proposed variable combination is theoretically coherent rather than a simple variable collage.

## License

MIT

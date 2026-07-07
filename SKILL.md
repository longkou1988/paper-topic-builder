---
name: paper-topic-builder
description: Generate evidence-based empirical management research topics from a Zotero Collection, subcollection, tag, or fallback bibliography/PDF corpus. Use when asked to classify management literature, extract findings and limitations, map quantitative variable roles or qualitative mechanisms, synthesize theory gaps, rebuild variable networks, propose empirical models, and evaluate topics from an SSCI management reviewer perspective.
---

# Paper Topic Builder

## Purpose

Use this skill to turn a specified Zotero literature set into evidence-based management empirical paper topics. The workflow reads the corpus, classifies each paper, extracts findings and limitations, maps quantitative variables and qualitative mechanisms, synthesizes theory gaps, recombines variable networks, generates topic cards and model candidates, and evaluates the topics from an SSCI management reviewer perspective.

The user may call this skill by the requested underscored name `paper_topic_builder`; the installed Codex skill name is the normalized hyphen form `paper-topic-builder`.

## Required Inputs

Before analysis, identify the requested source scope:

- Zotero Collection, subcollection path, tag, saved search, or item list.
- Optional focus constraints such as theory, journal set, country, industry, method, year range, or target journal direction.
- Optional fallback files: `.bib`, `.ris`, `.csv`, local PDF folder, or exported Zotero notes. Use these only when Zotero plugin access fails, permissions are insufficient, metadata is missing, or full text cannot be accessed through Zotero.

If the source scope is missing or ambiguous, ask one concise clarification question before proceeding.

## Mandatory Zotero Integration

The confirmed Zotero plugin Skill is installed at:

`/Users/long/.codex/plugins/cache/openai-curated-remote/zotero/0.1.2/skills/zotero/SKILL.md`

At the start of every Zotero-backed task, read and follow that Zotero Skill first. Use its confirmed helper before asking for exported files:

```bash
python3 /Users/long/.codex/plugins/cache/openai-curated-remote/zotero/0.1.2/skills/zotero/scripts/zotero.py status --json
```

Also inspect any currently exposed Zotero MCP/app tools if available, but do not guess tool names. The confirmed helper is the known local interface.

For a requested Zotero Collection, subcollection, saved search, tag, or item list:

1. Resolve the source scope through the confirmed Zotero Skill/helper or documented safe read-only local API routes from the Zotero plugin.
2. Retrieve metadata for every in-scope item where available: title, authors, year, journal, DOI, abstract, keywords, Zotero tags, collection path, notes or annotations, attachment PDF status, and full-text content.
3. If a PDF attachment exists, retrieve full text through the Zotero helper/API where possible; this workflow explicitly requires PDF/full-text access for evidence extraction.
4. If only metadata or abstract is available, mark the paper as `仅基于摘要分析`.
5. If the PDF is missing, inaccessible, unreadable, incomplete, or garbled, mark `全文不可用` with the reason.
6. If Zotero cannot be accessed, permissions are insufficient, or the requested scope cannot be resolved after using the confirmed plugin capability, state the exact gate and switch to fallback inputs in this order: `.bib`, `.ris`, `.csv`, local PDF folder.

Never fabricate literature facts, variable names, theoretical foundations, findings, DOI, journal names, or evidence text.

## Workflow

1. **Source Intake and Evidence Ledger**
   - Read the Zotero scope first; use fallback files only when necessary.
   - Assign stable `Paper_ID` values.
   - Build an evidence ledger linking every substantive extraction to `Paper_ID`, section, evidence text, source type, and confidence.
   - Keep direct quoted evidence short and use paraphrase for synthesis.

2. **Literature Type Classification**
   - Classify each paper as quantitative, qualitative, mixed methods, theory, review, method, or meta-analysis.
   - Base the judgment on paper content such as abstract, method, data, sample, analysis, findings, results, and discussion.
   - If evidence is insufficient, mark low confidence and write `不足以判断` for unsupported fields.

3. **General Literature Matrix**
   - Fill `output/literature_matrix.xlsx` using the schema in `references/extraction-schema.md`.
   - Include research topic, background, object, context, country or region, theory, research question, method, sample, data type, findings, contributions, limitations, future research, and extendable opportunities.

4. **Quantitative Variable Role Extraction**
   - For quantitative and relevant mixed-method papers, extract independent variables, dependent variables, mediators, moderators, controls, dimensions, moderated mediation or mediated moderation structures, hypotheses, significant and non-significant paths, inconsistent directions, measurement sources, and analysis methods.
   - Each row in `output/variable_role_matrix.xlsx` must include evidence from model figures, hypothesis sections, methods, measurement sections, results tables, or discussion.

5. **Qualitative Mechanism Extraction**
   - For qualitative and relevant mixed-method papers, extract cases, field setting, interviewees, coding approach, first-order concepts, second-order themes, aggregate dimensions, process mechanisms, boundary conditions, contributions, and convertible quantitative variables or paths.
   - Write results to `output/qualitative_mechanism_matrix.xlsx`.

6. **Theory Gap Analysis**
   - Read all extracted matrices and identify theory, mechanism, boundary condition, context, method, conflicting result, variable-role, and practical-problem gaps.
   - Write `output/theory_gap_matrix.xlsx` with supporting papers and evidence.

7. **Variable Network and Model Recombination**
   - Build a variable network from `variable_role_matrix.xlsx`.
   - Identify high-frequency IVs, DVs, mediators, moderators, overused variables, role-repositioning candidates, rarely combined but theoretically connectable variables, and antecedent-mechanism-outcome-boundary-condition combinations.
   - Write `output/variable_network_summary.md` and `output/model_candidates.md`.

8. **Topic Generation and Reviewer Evaluation**
   - Generate at least 10 management empirical topic cards in `output/topic_cards.md`.
   - Select the top 3 topics and write `output/final_research_story.md`.
   - Evaluate every topic in `output/reviewer_evaluation.md` using SSCI management reviewer criteria.
   - Include next-step guidance for developing full Introduction and Hypotheses sections.

## Reference Files

Before creating outputs, read:

- `references/zotero-integration.md` for the confirmed Zotero plugin entry point, helper commands, scope resolution, and fallback gates.
- `references/extraction-schema.md` for required workbook columns and markdown structures.
- `references/analysis-rules.md` for classification criteria, confidence rules, gap synthesis, model recombination, topic generation, and reviewer scoring.

## Template Utility

When starting from an empty output folder, run:

```bash
python scripts/create_workbook_templates.py --output output
```

This creates the required Excel workbooks and markdown skeletons without dummy data. Fill the templates only with evidence-supported content.

## Required Outputs

Produce these files under `output/`:

1. `literature_matrix.xlsx`
2. `variable_role_matrix.xlsx`
3. `qualitative_mechanism_matrix.xlsx`
4. `theory_gap_matrix.xlsx`
5. `variable_network_summary.md`
6. `topic_cards.md`
7. `model_candidates.md`
8. `final_research_story.md`
9. `reviewer_evaluation.md`

## Completion Check

The task is complete only when:

- All 9 output files exist.
- Every extracted literature fact is traceable to Zotero metadata, PDF text, abstract, note, annotation, or fallback source.
- Unsupported fields are marked `不足以判断`; low-confidence judgments are explicitly marked.
- Quantitative variable roles include evidence section and confidence.
- Qualitative mechanisms separate first-order concepts, second-order themes, aggregate dimensions, and mechanisms when evidence permits.
- Topic cards explain why each variable combination is theoretically coherent rather than a simple拼接.
- The final story and reviewer evaluation include feasibility, publication risk, and practical next steps for Introduction and Hypotheses.

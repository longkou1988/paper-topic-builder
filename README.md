# Management Empirical Topic Builder

Management Empirical Topic Builder is a Codex Skill for generating evidence-based empirical management research topics from a Zotero literature collection.

It reads a specified Zotero Collection, subcollection, tag, saved search, or fallback bibliography/PDF corpus, then classifies papers, extracts findings and limitations, maps quantitative variable roles and qualitative mechanisms, synthesizes theory gaps, rebuilds variable networks, generates empirical model candidates, and evaluates topics from an SSCI management reviewer perspective.

中文介绍见 [README.zh-CN.md](README.zh-CN.md).  
English introduction: [README.en.md](README.en.md).

## What It Produces

The Skill is designed to create these outputs under `output/` during use:

- `literature_matrix.xlsx`
- `variable_role_matrix.xlsx`
- `qualitative_mechanism_matrix.xlsx`
- `theory_gap_matrix.xlsx`
- `variable_network_summary.md`
- `topic_cards.md`
- `model_candidates.md`
- `final_research_story.md`
- `reviewer_evaluation.md`

## Core Principle

The Skill is evidence-first. It must not invent literature facts, variables, theoretical foundations, findings, DOI, journal names, or evidence text. Unsupported fields are explicitly marked as insufficient to judge.

## Repository Layout

```text
.
├── SKILL.md
├── README.md
├── README.zh-CN.md
├── README.en.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── analysis-rules.md
│   ├── extraction-schema.md
│   └── zotero-integration.md
└── scripts/
    └── create_workbook_templates.py
```

## License

MIT License. See [LICENSE](LICENSE).

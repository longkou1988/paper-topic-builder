# Extraction Schemas

Use these schemas for the required Excel workbooks and markdown files. Add extra columns only when they improve traceability; do not remove required columns.

## `literature_matrix.xlsx`

Sheet: `literature_matrix`

Columns:

- `Paper_ID`
- `Zotero_Key`
- `Title`
- `Authors`
- `Year`
- `Journal`
- `DOI`
- `Abstract`
- `Keywords`
- `Zotero_Tags`
- `Collection_Path`
- `Attachment_Status`
- `Analysis_Basis`
- `Research_Type`
- `Type_Evidence`
- `Type_Confidence`
- `Research_Topic`
- `Research_Background`
- `Research_Object`
- `Research_Context`
- `Country_Region`
- `Theoretical_Foundation`
- `Core_Research_Question`
- `Research_Method`
- `Sample_Source`
- `Sample_Size`
- `Data_Type`
- `Core_Findings`
- `Theoretical_Contribution`
- `Practical_Contribution`
- `Limitations`
- `Future_Research_Directions`
- `Extendable_Research_Opportunities`
- `Evidence_Sections`
- `Notes`

## `variable_role_matrix.xlsx`

Sheet: `variable_role_matrix`

One row per variable role, path, or model component where possible.

Columns:

- `Paper_ID`
- `Title`
- `Year`
- `Theory`
- `Context`
- `Variable_Name`
- `Variable_Role`
- `Construct_Level`
- `Hypothesized_Path`
- `Result`
- `Path_Direction`
- `Measurement_Source`
- `Analysis_Method`
- `Model_Structure`
- `Evidence_Text`
- `Evidence_Section`
- `Evidence_Source`
- `Confidence`

Allowed `Variable_Role` examples: `Independent Variable`, `Dependent Variable`, `Mediator`, `Moderator`, `Control Variable`, `Dimension`, `Second-order Construct`, `Moderated Mediation`, `Mediated Moderation`, `Path`.

Allowed `Result` examples: `Significant`, `Non-significant`, `Opposite direction`, `Mixed`, `Not tested`, `不足以判断`.

## `qualitative_mechanism_matrix.xlsx`

Sheet: `qualitative_mechanism_matrix`

Columns:

- `Paper_ID`
- `Title`
- `Year`
- `Research_Object`
- `Research_Setting`
- `Case_Count`
- `Interviewees`
- `Coding_Method`
- `First_Order_Concepts`
- `Second_Order_Themes`
- `Aggregate_Dimensions`
- `Process_Mechanism`
- `Boundary_Conditions`
- `Theoretical_Contribution`
- `Convertible_Quantitative_Variables`
- `Convertible_Paths`
- `Convertible_Moderators`
- `Evidence_Text`
- `Evidence_Section`
- `Confidence`

## `theory_gap_matrix.xlsx`

Sheet: `theory_gap_matrix`

Columns:

- `Gap_ID`
- `Gap_Type`
- `Gap_Statement`
- `Supporting_Papers`
- `Evidence_Texts`
- `Affected_Theory`
- `Variables_Involved`
- `Contexts_Involved`
- `Methodological_Basis`
- `Why_It_Matters`
- `Topic_Implication`
- `Confidence`

Allowed `Gap_Type` values: `Theory`, `Mechanism`, `Boundary Condition`, `Context`, `Method`, `Conflicting Result`, `Variable Role`, `Practical Problem`.

## `variable_network_summary.md`

Required sections:

1. `# Variable Network Summary`
2. `## Corpus Scope and Evidence Limits`
3. `## High-Frequency Independent Variables`
4. `## High-Frequency Dependent Variables`
5. `## High-Frequency Mediators`
6. `## High-Frequency Moderators`
7. `## Overused or Low-Innovation Variables`
8. `## Role-Repositioning Opportunities`
9. `## Rare but Theoretically Connectable Combinations`
10. `## Antecedent-Mechanism-Outcome-Boundary Models`

## `model_candidates.md`

For each model candidate include:

- Model name
- Management problem
- Research object and context
- Antecedent, mechanism, outcome, boundary condition
- Theoretical rationale
- Why it is not simple variable拼接
- Suggested empirical method
- Data source suggestion
- Publication risk
- Evidence base and confidence

## `topic_cards.md`

Generate at least 10 topics. Each topic must include:

1. Topic title
2. Core research question
3. Research object
4. Research context
5. Theoretical foundation
6. Independent variable
7. Dependent variable
8. Mediator
9. Moderator
10. Control variables
11. Theoretical story chain
12. Research hypotheses
13. Method suggestions
14. Data source suggestions
15. Innovation points
16. Feasibility
17. Publication risk
18. Suitable journal direction

## `final_research_story.md`

Select the top 3 topics. For each include:

1. Chinese title
2. English title
3. Research background
4. Practical management problem
5. Theory gap
6. Core research question
7. Theoretical foundation
8. Model structure
9. Hypothesis logic
10. Variable measurement suggestions
11. Data collection suggestions
12. Analysis method suggestions
13. Theoretical contribution
14. Practical contribution
15. Reviewer risks
16. Revision suggestions

End with `## Next Steps for Introduction and Hypotheses`.

## `reviewer_evaluation.md`

For every topic include:

- Theory contribution score: 1-5
- Practical significance score: 1-5
- Model clarity score: 1-5
- Method feasibility score: 1-5
- Data availability score: 1-5
- Novelty score: 1-5
- Publication risk: `低`, `中`, or `高`
- Overall recommendation: `强烈推荐`, `推荐`, `谨慎推荐`, or `不推荐`
- Reviewer-style rationale

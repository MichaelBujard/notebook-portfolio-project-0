# Project Status

Last updated: August 9, 2026, at commit `66ba471` (`Complete Section 8.1 state-to-state comparison`).

This file contains working context for future project sessions. Update it after each completed analysis section or other major checkpoint. Public-facing project background remains in `README.md`, and collaboration rules remain in `AGENTS.md`.

## Current State

- Sections 1–7 are complete: setup, data loading, inspection, cleaning, preparation, and validation.
- Explicit data-type validation is implemented in Section 6.5 and passes for all cleaned DataFrames.
- Section 8.1, State-to-State Comparison, is complete.
- The next task is Section 8.2, State-to-U.S. Comparison.
- Sections 8.3–8.6, conclusions, and the final limitations section remain to be completed.

## Project Objective

Complete a Python data-analysis portfolio project examining food insecurity in the United States. USDA Economic Research Service data is the primary source. World Bank undernourishment data supplies limited international context.

The analysis addresses these questions:

1. How does food insecurity differ among California, Texas, Iowa, New York, and Louisiana?
2. How do those states compare with the U.S. overall?
3. How does food insecurity vary by education level?
4. How does food insecurity vary by employment group?
5. How does food insecurity vary by disability status?
6. How do the U.S., Canada, and Mexico compare on World Bank undernourishment estimates?

## Prepared Analysis Tables

- `state_us_analysis_df`: 102 rows; six geographies across 17 overlapping three-year periods. Expected grain: one row per geography per three-year period.
- `educ_analysis_df`: 32 rows; four education categories across 2017–2024. Expected grain: one row per education category per year.
- `emp_analysis_df`: 56 rows; seven employment categories across 2017–2024. Expected grain: one row per employment category per year.
- `dis_analysis_df`: 32 rows; four disability categories across 2017–2024. Expected grain: one row per disability category per year.
- `wb_context_df`: 69 rows; the United States, Canada, and Mexico across 2001–2023. Expected grain: one row per country per year.

## Methodological Guardrails

- USDA state estimates are three-year averages.
- Adjacent state periods overlap by two years and are not independent annual observations. Do not describe their movement as independent year-to-year change.
- USDA state margins of error are 90-percent confidence margins.
- State estimates and national education, employment, and disability estimates must remain analytically separate. National subgroup patterns cannot explain or quantify state differences.
- USDA household food insecurity and World Bank undernourishment are related but distinct concepts. World Bank results provide context rather than validation of USDA results.
- Validate table grain, category coverage, missing values, duplicates, and relevant data types before interpreting or plotting a derived table.

## Analysis and Visualization Conventions

- Organize each subsection as table, validation, visualization, and written interpretation.
- Use the shared seaborn `whitegrid` theme and colorblind palette defined at the beginning of Section 8.
- Use “Estimated” in chart titles for survey estimates.
- Use full state names in presentation tables and charts.
- Use the established `state_palette` whenever color distinguishes state series.
- Use a consistent neutral treatment for the U.S. reference in Section 8.2.
- Include units in axis labels and disclose relevant uncertainty or omitted uncertainty in chart notes.
- Prefer broad descriptive patterns over causal claims or unsupported statements of statistical significance.

## Completed Section 8.1

Section 8.1 contains:

- A latest-period comparison table for 2022–2024 and its validation.
- A horizontal bar chart with USDA 90-percent margins of error.
- A historical 17-by-5 prevalence table and validation of its 85-row source table.
- A five-state historical line chart covering 2006–2008 through 2022–2024.
- Written interpretations for both views.

Confirmed findings:

- Louisiana and Texas had the highest 2022–2024 point estimates, 17.7 percent and 17.6 percent, and should not be ranked definitively against each other given their uncertainty.
- New York was intermediate; California and Iowa had the two lowest latest-period point estimates.
- Across all 17 periods, either Texas or Louisiana had the highest point estimate.
- Texas ranked highest in the first six periods. Louisiana ranked highest from 2012–2014 through 2019–2021. Texas ranked highest again in 2020–2022 and 2021–2023, followed by a near tie in 2022–2024.
- Iowa had the lowest point estimate in 15 of 17 periods.
- All five states had higher point estimates in 2022–2024 than in 2019–2021.

These historical findings are descriptive because adjacent periods overlap and the historical chart omits margins of error for readability.

## Next Steps: Section 8.2

Answer: *How do the selected states compare with the U.S. overall?*

Recommended sequence:

1. Create a 17-row U.S. reference table from the `U.S. total` observations.
2. Validate that the U.S. table contains exactly one observation per period.
3. Merge the U.S. estimate onto the 85 selected-state observations using an explicit many-to-one merge.
4. Derive each state’s difference from the U.S. estimate in percentage points.
5. Validate the resulting 85-row table: five states, 17 periods per state, no missing U.S. matches, and no duplicate state-period pairs.
6. Present the latest-period state-versus-U.S. comparison.
7. Create a historical difference-from-U.S. chart with a neutral zero reference line and the established state colors.
8. Interpret point-estimate differences cautiously. Use official USDA results before making claims about statistical significance.
9. Add the Section 8.2 findings and limitations in Markdown.
10. Restart the kernel, run the notebook top-to-bottom, review the rendered outputs, and create a checkpoint.

Latest point-estimate differences from the U.S. are Louisiana +4.4, Texas +4.3, New York +0.7, California −0.8, and Iowa −2.5 percentage points.

Before including significance claims, confirm them from the official USDA report. For 2022–2024, USDA reported Louisiana and Texas statistically above the U.S. average, Iowa statistically below it, and California and New York not statistically different from it for overall food insecurity.

## Remaining Sequence

1. Section 8.2: State-to-U.S. comparison.
2. Section 8.3: Education comparison.
3. Section 8.4: Employment comparison.
4. Section 8.5: Disability comparison.
5. Section 8.6: World Bank context.
6. Section 9: Conclusions.
7. Section 10: Final limitations.
8. Final notebook run, visual review, README refresh, and project cleanup.

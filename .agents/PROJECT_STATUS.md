# Project Status

Last updated: August 9, 2026.

This file contains working context for future project sessions. Update it after each completed analysis section or other major checkpoint. Public-facing project background remains in `README.md`, and collaboration rules remain in `AGENTS.md`.

## Current State

- Sections 1–7 are complete: setup, data loading, inspection, cleaning, preparation, and validation.
- Explicit data-type validation is implemented in Section 6.5 and passes for all cleaned DataFrames.
- Section 8.1, State-to-State Comparison, is complete.
- Section 8.2, State-to-U.S. Comparison, is complete.
- Section 8.3, Education Comparison, is complete.
- The notebook has been restarted and run top-to-bottom after completing Section 8.3: all 125 code cells executed in order with no saved errors.
- The immediate next task is Section 8.4, Employment Comparison.
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
- `us_reference_df`: 17 rows; one U.S. total observation per three-year period.
- `state_vs_us_df`: 85 rows; five states across 17 periods with the matching U.S. estimate and the state-minus-U.S. point-estimate difference. Expected grain: one row per state per three-year period.
- `latest_state_vs_us_df`: five rows; one selected-state comparison with the U.S. total for 2022–2024.
- `educ_analysis_df`: 32 rows and four columns; four education categories across 2017–2024. Expected grain: one row per education category per year.
- `emp_analysis_df`: 56 rows and four columns; seven employment categories across 2017–2024. Expected grain: one row per employment category per year.
- `dis_analysis_df`: 32 rows and four columns; four disability categories across 2017–2024. Expected grain: one row per disability category per year.
- `wb_context_df`: 69 rows; the United States, Canada, and Mexico across 2001–2023. Expected grain: one row per country per year.

## Methodological Guardrails

- USDA state estimates are three-year averages.
- Adjacent state periods overlap by two years and are not independent annual observations. Do not describe their movement as independent year-to-year change.
- USDA state margins of error are 90-percent confidence margins.
- Overall food-insecurity prevalence is the primary outcome throughout the state, education, employment, and disability analyses. Very low food security is a more severe subset but is outside the current analytical scope.
- State estimates and national education, employment, and disability estimates must remain analytically separate. National subgroup patterns cannot explain or quantify state differences.
- USDA household food insecurity and World Bank undernourishment are related but distinct concepts. World Bank results provide context rather than validation of USDA results.
- Validate table grain, category coverage, missing values, duplicates, and relevant data types before interpreting or plotting a derived table.

## Analysis and Visualization Conventions

### Standard EDA Section Structure

- Begin each numbered EDA section with its project question, source analysis table, and concise analytical purpose.
- Immediately below the section introduction, define shared section-level configuration in a dedicated setup cell. This includes category orders, label mappings, and palettes used later in the section. Define each shared object once and reuse it; do not create a custom palette when color does not encode categories or series.
- When both views are analytically useful, organize the section into a latest-period or latest-year subsection followed by a historical subsection.
- Within each analytical subsection, use this order:
  1. Create and display the presentation or derived table from an already validated analysis-ready DataFrame.
  2. Validate the table before plotting or interpreting it.
  3. Create and visually inspect the chart.
  4. Add a Markdown interpretation grounded in the validated values and rendered chart.
- After completing a numbered EDA section, review the section as a whole, restart the kernel, run the notebook top-to-bottom, inspect saved outputs and execution order, update this status file, and create a Git checkpoint.

### Table and Validation Conventions

- State the intended grain through the construction and validation: one row per relevant category and time period unless otherwise documented.
- Validate proportionate properties such as shape, expected category and period coverage, presentation order, missing values, duplicates, and derived calculations.
- Use explicit category-order lists for ordered tables and charts, and validate both category coverage and final presentation order.

### Visualization and Interpretation Conventions

- Use the shared seaborn `whitegrid` theme and colorblind palette defined at the beginning of Section 8.
- Use a single consistent color for a one-series comparison. When color distinguishes categories or series, define a section-specific mapping near the top of that section and reuse it.
- Use “Estimated” in chart titles for survey estimates.
- Include units in axis labels and disclose relevant uncertainty or omitted uncertainty in chart notes.
- Use direct value labels only when they materially improve interpretation, such as signed differences around a reference; avoid redundant labels when a readable axis and nearby table already provide the values.
- Use full state names in presentation tables and charts, the established `state_palette` for state series, and a consistent neutral treatment for the U.S. reference in Section 8.2.
- Interpret exact latest-period values and broad historical patterns, but avoid causal claims or statements of statistical significance unless supported by the source data and an appropriate verified method.

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

## Completed Section 8.2

Answer: *How do the selected states compare with the U.S. overall?*

Completed work:

- Created and validated a 17-row U.S. reference table with exactly one observation per period.
- Merged the U.S. reference onto the 85 selected-state observations with an explicit many-to-one merge.
- Derived and validated each state’s point-estimate difference from the U.S. total in percentage points.
- Created and validated the five-row latest-period comparison table.
- Created a horizontal diverging bar chart of the 2022–2024 point-estimate differences. The chart uses established state colors, a neutral zero reference, a symmetric scale, direct value labels, and a note explaining that uncertainty for the differences cannot be derived from the published margins of error alone.
- Added the latest-period interpretation in Markdown.
- Created and validated the 17-by-5 historical difference table for Section 8.2.2.
- Created a five-state historical line chart of point-estimate differences from the U.S. covering 2006–2008 through 2022–2024. The chart uses the established state colors, a neutral zero reference, a symmetric scale, full three-year period labels, and a note addressing overlap, unavailable difference uncertainty, and statistical significance.
- Added a cautious historical interpretation in Markdown.
- Reviewed the complete section for structure, calculations, chart labeling, and analytical accuracy; no incorrect calculations or unsupported claims were identified.
- Restarted the kernel and ran the notebook top-to-bottom. All 118 code cells have sequential execution counts from 1 through 118, with no saved error outputs.

Latest point-estimate differences from the U.S. are Louisiana +4.4, Texas +4.3, New York +0.7, California −0.8, and Iowa −2.5 percentage points.

Confirmed historical findings:

- Texas was above the U.S. point estimate in all 17 periods, while Iowa was below it in all 17 periods.
- Louisiana was below the U.S. estimate in the first four periods and above it from 2010–2012 onward. Its largest difference was +5.3 percentage points in 2014–2016.
- California was modestly above the U.S. estimate during several early periods and below it from 2012–2014 onward.
- New York generally remained relatively close to the U.S. estimate and appeared on both sides of the U.S. reference.

These are descriptive point-estimate patterns. Adjacent periods overlap by two years, and uncertainty for state-minus-U.S. differences cannot be derived from the published margins of error alone.

## Completed Section 8.3

Answer: *How does food insecurity vary by education level in the U.S.?*

Completed work:

- Narrowed `educ_analysis_df`, `emp_analysis_df`, and `dis_analysis_df` to four analysis-ready columns by removing the out-of-scope `very_low_food_security_percent` field. The cleaned source data still preserve that measure.
- Updated and reran the Section 7 validations. The three subgroup tables retain their expected row counts, category coverage, grain, and absence of missing values or duplicate year-category pairs.
- Documented in the README, with official USDA ERS citations, that very low food security is the more severe subset of food insecurity and that this project consistently focuses on overall food-insecurity prevalence.
- Defined and validated the ordered 2024 education comparison table with four categories and one row per category.
- Created a horizontal bar chart of estimated 2024 food-insecurity prevalence by education level, using a consistent single-color treatment, percentage units, and a note that the source file does not provide margins of error for these subgroup estimates.
- Added and reviewed a cautious latest-year interpretation that describes association rather than causation and does not assess statistical significance.
- Created and validated an 8-by-4 historical education table covering 2017–2024, with years and education categories in the intended presentation order.
- Created a four-series historical line chart with a zero baseline, annual year labels, the established education order, and a note addressing unavailable margins of error.
- Added and reviewed a historical interpretation describing the persistent ordering and broad movement of the point estimates without causal or statistical-significance claims.
- Reviewed the complete section for structure, calculations, chart labeling, and analytical accuracy; no incorrect calculations or unsupported claims were identified.
- Restarted the kernel and ran the notebook top-to-bottom. All 125 code cells have sequential execution counts from 1 through 125, with no saved error outputs.

Confirmed 2024 findings:

- Estimated food-insecurity prevalence was 30.4 percent for less than high school, 21.7 percent for high school, 18.3 percent for some college, and 6.1 percent for college or more.
- The college-or-more estimate was 24.3 percentage points below the less-than-high-school estimate.
- The ordered pattern is descriptive and does not establish that educational attainment caused the differences.
- Statistical significance is not assessed because the source file does not provide margins of error for these subgroup estimates.

Confirmed historical findings:

- The less-than-high-school category had the highest point estimate in every year from 2017 through 2024, while college or more had the lowest.
- The high-school estimate remained above the some-college estimate in every year.
- Estimates were relatively stable or generally declined from 2017 through 2021, and all four categories had higher point estimates in 2022 than in 2021.
- From 2022 through 2024, the less-than-high-school estimate remained near 30 percent, the high-school and some-college estimates increased to 21.7 and 18.3 percent, and the college-or-more estimate ended at 6.1 percent.
- These patterns are descriptive because margins of error are unavailable and statistical significance is not assessed.

## Immediate Next Steps

1. Begin Section 8.4, Employment Comparison, using the validated `emp_analysis_df` table.
2. Confirm the intended employment-category ordering and select the latest-year and historical views needed to answer the question.
3. Preserve the established sequence of table, validation, visualization, and written interpretation.
4. Keep national employment patterns analytically separate from the state comparisons in Sections 8.1 and 8.2.

## Remaining Sequence

1. Section 8.4: Employment comparison.
2. Section 8.5: Disability comparison.
3. Section 8.6: World Bank context.
4. Section 9: Conclusions.
5. Section 10: Final limitations.
6. Final notebook run, visual review, README refresh, and project cleanup.

# Food Insecurity in the United States

This Python data-analysis portfolio project examines household food insecurity in the United States using public data from the USDA Economic Research Service (ERS). It compares selected states with one another and with the U.S. total, then examines national patterns by education, employment, and disability status. World Bank/FAO undernourishment data supplies limited international context for the United States, Canada, and Mexico.

The completed analysis is in [`notebooks/food_insecurity_analysis.ipynb`](notebooks/food_insecurity_analysis.ipynb).

## Project Goals

1. Practice loading, inspecting, cleaning, reshaping, joining, validating, and analyzing real-world data with Python and pandas.
2. Create clear tables and visualizations that answer defined analytical questions.
3. Communicate findings, uncertainty, and limitations without making unsupported causal or statistical-significance claims.

## Analytical Questions

1. How does food insecurity differ among California, Texas, Iowa, New York, and Louisiana?
2. How do those states compare with the U.S. overall?
3. How does food insecurity vary by education level in the U.S.?
4. How does food insecurity vary by employment group in the U.S.?
5. How does food insecurity vary by disability status in the U.S.?
6. How do the U.S., Canada, and Mexico compare on World Bank undernourishment estimates, and what metadata helps interpret that comparison?

The five states were selected because they are personally meaningful to the analyst through family and other significant ties. They are not intended to represent all U.S. states.

## Data Sources

### USDA Economic Research Service

USDA ERS is the primary source. The project uses:

- `foodsecurity-state-2024.csv` for state and U.S. estimates covering 17 overlapping three-year periods from 2006–2008 through 2022–2024.
- `foodsecurity-educ-emp-dis-2024.csv` for annual national estimates by education, employment, and disability status from 2017 through 2024.

USDA defines food-insecure households as including households with low food security and very low food security. Very low food security is the more severe range of food insecurity. This project consistently analyzes overall food-insecurity prevalence.

- [USDA ERS: Interactive Charts and Highlights](https://www.ers.usda.gov/topics/food-nutrition-assistance/food-security-in-the-us/interactive-charts-and-highlights)
- [USDA ERS: Key Statistics and Graphics](https://www.ers.usda.gov/topics/food-nutrition-assistance/food-security-in-the-us/key-statistics-graphics)
- [USDA ERS: Measurement](https://www.ers.usda.gov/topics/food-nutrition-assistance/food-security-in-the-us/measurement)

### World Bank and FAO

World Bank indicator `SN.ITK.DEFC.ZS`, *Prevalence of undernourishment (% of population)*, provides annual observations for the United States, Canada, and Mexico from 2001 through 2023. The indicator is produced by the Food and Agriculture Organization of the United Nations (FAO) and distributed through the World Bank.

Undernourishment and USDA household food insecurity are related but distinct concepts. The international results provide context rather than validation of the USDA findings.

- [World Bank indicator](https://data.worldbank.org/indicator/SN.ITK.DEFC.ZS)
- [World Bank DataBank Metadata Glossary](https://databank.worldbank.org/metadataglossary/sustainable-development-goals-%28sdgs%29/series/SN.ITK.DEFC.ZS)
- [FAO: Computing the Prevalence of Undernourishment](https://www.fao.org/measuring-hunger/access-to-dietary-energy/computing-the-pou/en)

## Workflow

The notebook documents the complete analytical workflow:

1. Set up the environment and load the source files.
2. Inspect shapes, columns, data types, missing values, categories, and duplicates.
3. Standardize column names and national geography labels while preserving meaningful missing values.
4. Prepare and validate analysis-ready state, national subgroup, and World Bank tables.
5. Compare the latest available estimates and historical patterns.
6. Visualize the results and interpret them within the available uncertainty and metadata.
7. Summarize conclusions and limitations.

Validation checks cover table grain, expected category and period coverage, missing values, duplicates, presentation order, derived calculations, and relevant data types.

## Key Findings

- In 2022–2024, Louisiana and Texas had the highest food-insecurity point estimates among the five selected states, at 17.7 percent and 17.6 percent. Iowa had the lowest, at 10.8 percent. Louisiana and Texas were each more than four percentage points above the U.S. estimate, while California and Iowa were below it.
- Across all 17 overlapping state periods, Texas remained above the U.S. point estimate and Iowa remained below it. All five selected states had higher point estimates in 2022–2024 than in 2019–2021.
- In 2024, national food-insecurity estimates decreased across successively higher education categories, from 30.4 percent for less than high school to 6.1 percent for college or more.
- Unemployed, Disabled, and Part-time economic reasons had the three highest employment-group point estimates in 2024. Full-time and Retired had the two lowest.
- Not in labor force due to disability had the highest disability-category estimate in 2024, at 34.9 percent, followed by Other disability among adults 18–64 at 27.3 percent.
- Mexico's reported undernourishment prevalence declined from 3.6 percent in 2018 to 2.7 percent in 2023. The United States and Canada were displayed as 2.5 percent throughout 2001–2023, but World Bank metadata states that values shown as 2.5 may represent prevalence below 2.5 percent.

These findings are descriptive associations and patterns, not causal conclusions.

## Limitations

- The five selected states are not a representative sample of all states.
- USDA state estimates are overlapping three-year averages. Adjacent periods share two years and are not independent annual observations.
- USDA publishes 90-percent margins of error for the state estimates, but uncertainty for state-minus-U.S. differences cannot be calculated from those margins alone.
- The education, employment, and disability tables contain national household estimates. They cannot explain state differences or show how the characteristics interact within the same households.
- The source file does not provide margins of error for the national subgroup estimates, so statistical significance is not assessed.
- The analysis does not control for income, household composition, geography, policy conditions, or other potentially related factors.
- World Bank undernourishment and USDA household food insecurity measure different concepts and cannot be compared directly.
- World Bank values displayed as 2.5 may represent prevalence below 2.5 percent. The downloaded World Bank file also does not provide uncertainty intervals.
- This project does not examine the country-specific FAO inputs closely enough to determine whether input differences affect the international comparison.

## Repository Structure

```text
notebook-portfolio-project-0/
|-- data/
|   |-- raw/
|       |-- usda_ers_food_security/
|       |-- world_bank_undernourishment/
|-- notebooks/
|   |-- food_insecurity_analysis.ipynb
|-- README.md
```

The raw source files are retained so the notebook can reproduce the prepared tables and analysis from the downloaded data.

## Tools

- Python
- Jupyter Notebook or JupyterLab
- pandas
- NumPy
- matplotlib
- seaborn

## Reproducing the Analysis

1. Clone or download this repository.
2. Install Python and the tools listed above.
3. Open `notebooks/food_insecurity_analysis.ipynb` with the working directory set to `notebooks/`.
4. Restart the kernel and run all cells from top to bottom.

The completed saved notebook contains 146 sequentially executed code cells with no saved errors.

## Status

The project is complete. The final notebook contains 146 sequentially executed code cells with no saved errors. The analysis, conclusions, limitations, documentation, and final review are complete.

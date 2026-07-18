# Food Insecurity in the United States

This project explores food insecurity in the United States using public data from the USDA Economic Research Service. The focus is on how food insecurity varies by state, education, employment, and disability. We will use World Bank undernourishment data for international context, but USDA data is the primary source for most analyses.

This is for the Codecademy Python for Data Science portfolio project.

## Goals

1. Practice using Python and pandas.
2. Clean, inspect, prepare, and analyze real-world data.
3. Communicate findings from real-world data and limitations of analysis.

The analysis focuses on these questions:

1. *How do food insecurity rates differ among California, Texas, Iowa, New York, and Louisiana?*
	- Use: `foodsecurity-state-2024.csv`
	- Analysis: filter states + compare prevalence rates
2. *How do selected states compare with the U.S. overall?*
	- Use: `foodsecurity-state-2024.csv` and `foodsecurity-all-households-2024.csv`
	- Analysis: compare each selected state against `U.S. total`
3. *How does food insecurity vary by education level in the U.S.?*
	- Use: `foodsecurity-educ-emp-dis-2024.csv`
	- Analysis: filter education rows + compare percentages
4. *How does food insecurity vary by employment group in the U.S.?*
	- Use: `foodsecurity-educ-emp-dis-2024.csv`
	- Analysis: filter employment rows + compare percentages
5. *How does food insecurity vary by disability status in the U.S.?*
	- Use: `foodsecurity-educ-emp-dis-2024.csv`
	- Analysis: filter disability rows + compare percentages
6. *How does the U.S. compare with Canada and Mexico on undernourishment, and what World Bank metadata can be used to interpret that comparison?*
	- Use: World Bank files in `.\data\raw\world_bank_undernourishment\.`
	- Analysis: compare the U.S. with Canada and Mexico

## Scope

Focuses on household food insecurity among the general U.S. population, zooming in on certain states.

The selected states for closer comparison are:

- California
- Texas
- Iowa
- New York
- Louisiana

These states were selected because they are personally meaningful to the analyst through family and other significant ties.

## Data Sources

### Primary Source: USDA Economic Research Service

The main data source is the USDA ERS Food Security in the U.S. data download. These files include food security statistics by household characteristics and by state.

Files used or expected to be used:

- `foodsecurity-state-2024.csv`
- `foodsecurity-all-households-2024.csv`
- `foodsecurity-educ-emp-dis-2024.csv`
- `foodsecurity-readme-2024.csv`

The state-level data uses 3-year averages.

Source link:

- https://www.ers.usda.gov/topics/food-nutrition-assistance/food-security-in-the-us/interactive-charts-and-highlights

### Secondary Source: World Bank

World Bank undernourishment data will be used to compare U.S., Canada, and Mexico undernourishment. This source measures a similar but distinct concept from USDA household food insecurity, so it can't directly validate the USDA data.

Source link:

- https://data.worldbank.org/indicator/SN.ITK.DEFC.ZS?locations=US

## Project Structure

```text
notebook-portfolio-project-0/
|-- data/
|   |-- raw/
|   |   |-- usda_ers_food_security/
|   |   |-- world_bank_undernourishment/
|   |-- processed/
|-- notebooks/
|-- outputs/
|   |-- figures/
|-- README.md
```

Additional folders or subfolders may be added later, as needed:

```text
data/processed/*
outputs/figures/
```

## Tools

This project will use, at minimum:

- Python
- Jupyter Notebook or JupyterLab
- pandas
- matplotlib
- seaborn

Python download link:

- https://www.python.org/downloads/release/python-3146/

## Analysis Plan


1. Data Collection
2. Get Set Up Off-Platform
3. Set Up the Project
4. Project Goals and Data Questions
5. Load and Inspect the Data
	- USDA datasets
6. Data Cleaning
	- Clean column names and check data types
7. Data Preparation
	- Identify the rows needed for state, education, employment, and disability analysis
8. EDA
	- Compare selected states with the U.S. total.
	- Compare food insecurity by education level.
	- Compare food insecurity by employment category.
	- Compare food insecurity by disability status.
	- Compare U.S. undernourishment with Mexico and Canada undernourishment rates using World Bank data.
	- Create clear charts and summary tables.
9. Write conclusions and note limitations.

## Notes and Already-Known Limitations

- USDA state estimates are reported as 3-year averages, not year-by-year
- When comparing selected states with annual U.S. overall estimates, the analysis aligns each USDA state 3-year period with the U.S. annual row for the period end year.
- Education and employment data may be national-level only, depending on the source and data collection method.
- Because education and employment data may be analyzed nationally rather than within each selected state, this project compares state-level and socioeconomic patterns separately. It does not claim that education or employment explains differences between states unless the data directly supports that.
- World Bank undernourishment data measures a different concept than USDA food insecurity and should only be used for perspective or broad context.

## Status

Cleaning and Section 7.1 are complete. Creating tables for analysis.

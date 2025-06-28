# Cleaned Aviation Data Analysis

## Overview
The `Cleaned_AviationData.csv` dataset provides a comprehensive view of aviation incidents from 1962 to 2022, focusing on four major aircraft manufacturers: Boeing, Airbus, Cessna, and Piper. With approximately 40,000–50,000 records and 33 columns, this pre-cleaned dataset enables analysis of aviation safety metrics, including incident counts, people involved, and injury severity (Fatal, Serious, Minor, Uninjured). This repository supports data-driven insights into safety trends, comparing general aviation (Cessna, Piper) versus commercial aviation (Boeing, Airbus), and is designed for use in visualization tools (e.g., Tableau, Power BI), statistical analysis (e.g., Python, R), or research. The accompanying Tableau dashboard (https://public.tableau.com/app/profile/hudheyfa.mohamud/viz/AviationAnalysisTableau/AviationIncidentAnalysis) and analysis notebook visualize key findings, answering critical business questions for aviation safety stakeholders.

## Business Understanding
### Stakeholder
The primary stakeholders are aviation safety regulators (e.g., FAA, NTSB), aircraft manufacturers (Boeing, Airbus, Cessna, Piper), and safety researchers. These groups aim to improve aviation safety by understanding incident patterns, reducing fatalities, and identifying high-risk factors.

### Key Business Questions
1. **Which aircraft makes have the highest incident counts, and how do general and commercial aviation compare?**
   - Helps prioritize safety interventions for high-incident manufacturers.
2. **How has the number of people involved in accidents and their injury severity changed over time (1962–2022)?**
   - Informs trends in safety improvements and identifies critical periods.
3. **What are the differences in injury severity (Fatal, Serious, Minor, Uninjured) across aircraft makes?**
   - Guides targeted safety measures for manufacturers with higher fatal outcomes.

## Data Understanding and Analysis
### Source of Data
- **File**: `Cleaned_AviationData.csv`
- **Origin**: Likely derived from the NTSB Aviation Accident Database, filtered to include only Boeing, Airbus, Cessna, and Piper incidents, and cleaned for consistency.
- **Size**: ~40,000–50,000 rows, 33 columns
- **Time Period**: 1962–2022

### Description of Data
The dataset includes detailed incident records with the following key columns:

| Column Name               | Data Type | Description                                      |
|---------------------------|-----------|--------------------------------------------------|
| `Event.Id`                | String    | Unique identifier for each incident              |
| `Event.Year`              | Integer   | Year of the incident (1962–2022)                |
| `Event.Date`              | Date      | Date of the incident                            |
| `Make`                    | String    | Aircraft manufacturer (Boeing, Airbus, Cessna, Piper) |
| `Model`                   | String    | Aircraft model (e.g., 737, A320, 172, PA-28)    |
| `Total.Fatal.Injuries`    | Numeric   | Number of fatal injuries (nulls set to 0)       |
| `Total.Serious.Injuries`  | Numeric   | Number of serious injuries (nulls set to 0)     |
| `Total.Minor.Injuries`    | Numeric   | Number of minor injuries (nulls set to 0)       |
| `Total.Uninjured`         | Numeric   | Number of uninjured people (nulls set to 0)     |
| `Broad.phase.of.flight`   | String    | Flight phase (e.g., Takeoff, Landing, Cruise)   |

*Note*: The dataset includes additional columns (up to 33) for context (e.g., `Location`, aircraft damage). Missing values were handled (e.g., nulls set to 0 for injuries), and `Make`/`Model` standardized (e.g., consistent casing).

### Visualizations
The following visualizations, created in Tableau and included in the analysis notebook and slides, highlight key insights:

1. **Injury Severity Breakdown (Stacked Bar Chart)**:
   - **Description**: Shows the number of people involved in accidents by make, segmented by injury type (Fatal, Serious, Minor, Uninjured).
   - **Insight**: Cessna and Piper involve ~50,000–100,000 people each, mostly uninjured (~70–80%) or with minor injuries (~10–20%). Boeing and Airbus involve fewer people (~5,000–10,000) but have higher fatal proportions (~20–30%).
   - **Use**: Answers the question of injury severity differences, highlighting commercial aviation’s higher fatality rates.

2. **People Involved by Year (Stacked Area Chart)**:
   - **Description**: Displays the total number of people involved in accidents per year (1962–2022), broken down by Fatal, Serious, Minor, and Uninjured.
   - **Insight**: Peaks in the 1970s–1980s (~5,000–10,000 people/year), with a decline toward 2022 (~1,000–2,000/year), driven by safety improvements. Uninjured dominate general aviation incidents.
   - **Use**: Addresses trends in people involved over time, showing reduced incident severity.

3. **Incidents by Make (Bar Chart)**:
   - **Description**: Shows the number of incidents (`COUNTD(Event.Id)`) for each make.
   - **Insight**: Cessna and Piper dominate (~15,000–20,000 incidents each) due to general aviation’s high flight volume; Boeing and Airbus have ~1,000–2,000 incidents each.
   - **Use**: Answers which makes have the highest incident counts, emphasizing general aviation’s prevalence.

*Note*: Visualizations use a `Make` filter (multi-select dropdown) for interactivity, allowing users to focus on specific manufacturers.

## Conclusion
### Summary of Conclusions
The analysis of `Cleaned_AviationData.csv` reveals critical aviation safety insights:
1. **General Aviation Dominance**: Cessna and Piper account for the majority of incidents (~80–90% combined) and people involved (~50,000–100,000 each), driven by their widespread use in general aviation (e.g., training, personal flights).
2. **Higher Severity in Commercial Aviation**: Boeing and Airbus have fewer incidents (~1,000–2,000 each) but a higher proportion of fatal injuries (~20–30% of people involved), reflecting the severity of commercial crashes.
3. **Safety Improvements Over Time**: The number of people involved in accidents peaked in the 1970s–1980s and declined significantly by 2022, indicating effective safety regulations and technological advancements.

These findings inform stakeholders on prioritizing safety measures for general aviation and addressing high-severity commercial incidents.

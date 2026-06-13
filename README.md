# Automation Readiness Analysis Using Stack Overflow Developer Survey Data

## Project Title

**From Manual Testing to Automation Readiness: A Secondary Analysis of Public Developer Survey Data and Open-Access Software Testing Literature**

## Project Overview

This repository contains the supporting data analysis files for a dissertation project examining automation-readiness indicators among QA and testing-related professionals.

The analysis was completed using **Google Colab** and Python. The project uses the 2025 Stack Overflow Developer Survey dataset to identify QA/test-oriented respondents and examine their technical profiles through available survey variables.

Because the dataset does not directly ask whether a respondent is a manual tester or whether they are fully ready for test automation, this study uses a **proxy-readiness approach**. Automation readiness is estimated indirectly through measurable indicators such as coding experience, professional experience, programming-language exposure, database exposure, platform/tool exposure, development-environment exposure, and AI/tooling exposure.

## Repository Structure

```text
Thesis-/
│
├── README.md
├── requirements.txt
├── stackoverflow_methodology_chapter4_analysis.ipynb   # main Google Colab notebook
│
├── data/
│   ├── filtered_qa_test_respondents.csv                # final filtered QA/test sample (343 respondents)
│   ├── experience_summary.csv                          # YearsCode and WorkExp summary
│   └── filtered_database_counts.csv                    # dataset filtering summary table
│
└── outputs/
    ├── charts/                                         # PNG charts used in Chapter 4
    └── tables/                                         # exported summary CSV tables
```

## Main Files

### `stackoverflow_methodology_chapter4_analysis.ipynb`

The main Google Colab notebook used for the analysis. It includes data loading, filtering, cleaning, summary statistics, proxy-readiness classification, and chart generation.

### `data/filtered_qa_test_respondents.csv`

The final filtered QA/test-oriented respondent sample used in the analysis (343 respondents). The sample includes respondents whose role or professional description relates to QA, software testing, test engineering, or quality assurance.

### `data/experience_summary.csv`

Summarises coding experience (`YearsCode`) and professional work experience (`WorkExp`) for the filtered QA/test sample.

### `data/filtered_database_counts.csv`

A **dataset filtering summary table**. It records the filtering steps and counts used to build the sample: total survey responses (49,191), responses with a valid DevType value (43,680), QA/test respondents matching "Developer, QA or test" (343), and the final usable QA/test sample (343). (Database-technology exposure among respondents is reported separately in the `top_DatabaseHaveWorkedWith.csv` output table.)

### `outputs/charts/`

Charts generated from the analysis, supporting the Chapter 4 findings (language exposure, database exposure, platform/tool exposure, development-environment exposure, AI/tooling exposure, and the proxy-readiness distribution).

### `outputs/tables/`

Exported summary tables produced during the analysis.

## Methodology Summary

### Dataset Filtering

The original 2025 Stack Overflow Developer Survey dataset includes respondents from many software and technology roles. To align the dataset with the dissertation topic, the data was filtered on the `DevType` field to identify respondents connected with QA and testing-related work (the value "Developer, QA or test").

After filtering, the final QA/test sample contained **343 respondents**.

### Proxy-Readiness Score

The dataset does not directly measure automation readiness or practical automation-testing competence, so a proxy-readiness score was used. It was calculated from available indicators including coding experience, professional work experience, programming-language exposure, database exposure, platform/tool exposure, development-environment exposure, and AI/tooling exposure.

Respondents with stronger combined technical indicators were classified as having **higher** proxy-readiness; those with fewer indicators were classified as **moderate** or **lower**. This should be understood as an estimated readiness profile, not a direct skills test.

## Key Results

The final filtered sample contained **343 QA/test-oriented respondents**.

The proxy-readiness classification showed:

- **66.18%** higher proxy-readiness (227 respondents);
- **13.12%** moderate proxy-readiness (45 respondents);
- **20.70%** lower proxy-readiness (71 respondents).

These results suggest that many QA/test-oriented professionals already show technical characteristics that may support a transition toward automation testing. However, because the analysis uses indirect indicators, the findings should not be interpreted as direct proof of automation competence.

## How to Run the Project in Google Colab

1. Open `stackoverflow_methodology_chapter4_analysis.ipynb` in Google Colab.
2. Upload the required CSV files into the Colab session (or mount Google Drive):
   `filtered_qa_test_respondents.csv`, `experience_summary.csv`, `filtered_database_counts.csv`. If the notebook uses the original survey dataset, upload it according to the file path used in the notebook.
3. Install any missing packages with `!pip install -r requirements.txt`.
4. Run all cells from top to bottom: load the dataset, filter QA/test respondents, clean variables, calculate descriptive statistics, calculate proxy-readiness categories, generate tables and charts, and export outputs.
5. Download or save the generated CSVs, tables, and charts from the Colab file panel.

## Requirements

```text
pandas
numpy
matplotlib
jupyter
openpyxl
```

## Academic Use Note

This project uses secondary public survey data. No primary data collection, interviews, questionnaires, or experiments were conducted. The analysis is descriptive and proxy-based; the dataset does not directly measure manual-testing background, automation competence, or workplace readiness, so the findings should be interpreted as an indirect readiness profile.

## Limitations

The main limitation is that the Stack Overflow Developer Survey dataset does not directly identify manual testers or directly assess automation-testing competence. The analysis depends on available survey variables and role/profile indicators, so the proxy-readiness score is useful for descriptive analysis but cannot prove actual automation skills or workplace performance.

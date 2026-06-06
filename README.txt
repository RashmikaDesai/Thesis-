# Automation Readiness Analysis Using Stack Overflow Developer Survey Data

## Project Title

**From Manual Testing to Automation Readiness: A Secondary Analysis of Public Developer Survey Data and Open-Access Software Testing Literature**

## Project Overview

This repository contains the supporting data analysis files for a dissertation project examining automation-readiness indicators among QA and testing-related professionals.

The analysis was completed using **Google Colab** and Python. The project uses the Stack Overflow Developer Survey dataset to identify QA/test-oriented respondents and examine their technical profiles through available survey variables.

Because the dataset does not directly ask whether a respondent is a manual tester or whether they are fully ready for test automation, this study uses a **proxy-readiness approach**. This means automation readiness is estimated indirectly through measurable indicators such as coding experience, professional experience, programming language exposure, database exposure, platform/tool exposure, development environment exposure, and AI/tooling exposure.

## Purpose of the Repository

This repository is provided to support transparency and reproducibility of the dissertation analysis. It includes the notebook, processed CSV files, output charts, tables, and instructions required to understand and rerun the analysis.

The repository supports:

- methodology explanation;
- dataset filtering process;
- Chapter 4 data analysis;
- charts and tables used in the findings;
- proxy-readiness classification;
- reproducibility of the Google Colab workflow.

## Repository Structure

```text
automation-readiness-project/
│
├── README.md
├── requirements.txt
│
├── notebook/
│   └── stackoverflow_methodology_chapter4_analysis.ipynb
│
├── data/
│   ├── filtered_qa_test_respondents.csv
│   ├── experience_summary.csv
│   └── filtered_database_counts.csv
│
├── outputs/
│   ├── charts/
│   └── tables/
│
└── src/
    └── analysis_pipeline.py
```

## Main Files

### `notebook/stackoverflow_methodology_chapter4_analysis.ipynb`

This is the main Google Colab notebook used for the analysis. It includes data loading, filtering, cleaning, summary statistics, proxy-readiness classification, and chart generation.

### `data/filtered_qa_test_respondents.csv`

This file contains the final filtered QA/test-oriented respondent sample used in the analysis. The sample includes respondents whose roles or professional descriptions relate to QA, software testing, test engineering, quality assurance, or test-oriented development.

### `data/experience_summary.csv`

This file summarises coding experience and professional work experience for the filtered QA/test-oriented respondent sample.

### `data/filtered_database_counts.csv`

This file summarises database exposure among the filtered QA/test-oriented respondents.

### `outputs/charts/`

This folder contains the charts generated from the analysis. These charts support Chapter 4 findings and may include language exposure, database exposure, platform/tool exposure, AI/tooling exposure, and proxy-readiness distribution.

### `outputs/tables/`

This folder contains exported summary tables produced during the analysis.

### `src/analysis_pipeline.py`

This optional Python script version of the workflow is included for users who want to inspect or run the analysis outside Google Colab.

## Methodology Summary

### Dataset Filtering

The original Stack Overflow Developer Survey dataset includes respondents from many software and technology roles. To align the dataset with the dissertation topic, the full dataset was filtered to identify respondents connected with QA and testing-related work.

The filtering process searched relevant role or professional description fields for QA/testing-related terms such as:

- QA;
- testing;
- software testing;
- test engineer;
- test automation;
- quality assurance;
- test-oriented development.

After filtering, the final QA/test-oriented sample contained **343 respondents**.

### Proxy-Readiness Score

The dataset does not directly measure automation readiness or practical automation-testing competence. Therefore, a proxy-readiness score was used.

The score was calculated from available indicators in the survey dataset, including:

- coding experience;
- professional work experience;
- programming language exposure;
- database exposure;
- platform and tool exposure;
- development environment exposure;
- AI/tooling exposure.

Respondents with stronger combined technical indicators were classified as having **higher proxy-readiness**. Respondents with fewer indicators were classified as having **moderate** or **lower proxy-readiness**.

This classification should be understood as an estimated readiness profile, not as a direct skills test.

## Chart Generation

Charts were generated in Google Colab using Python. The workflow calculated frequency counts, percentages, and descriptive statistics from the cleaned and filtered dataset.

The charts were used to show:

- common programming languages among QA/test-oriented respondents;
- database exposure;
- platform and tool exposure;
- development environment usage;
- AI/tooling exposure;
- distribution of respondents across proxy-readiness categories.

## Key Results

The final filtered sample contained **343 QA/test-oriented respondents**.

The proxy-readiness classification showed:

- **66.18%** higher proxy-readiness;
- **20.70%** moderate proxy-readiness;
- **13.12%** lower proxy-readiness.

These results suggest that many QA/test-oriented professionals already show technical characteristics that may support transition toward automation testing. However, because the analysis uses indirect indicators, the findings should not be interpreted as direct proof of automation competence.

## How to Run the Project in Google Colab

### Step 1: Open the Notebook

Open the notebook file:

```text
notebook/stackoverflow_methodology_chapter4_analysis.ipynb
```

The notebook can be opened in Google Colab by uploading it manually or by opening it from the GitHub repository.

### Step 2: Upload or Mount the Data Files

Upload the required CSV files into the Colab session or mount Google Drive if the files are stored there.

Required processed files:

```text
filtered_qa_test_respondents.csv
experience_summary.csv
filtered_database_counts.csv
```

If the notebook uses the original Stack Overflow Developer Survey dataset, upload the original dataset file according to the file path used in the notebook.

### Step 3: Install Required Packages

Most required packages are already available in Google Colab. If any package is missing, run:

```python
!pip install -r requirements.txt
```

### Step 4: Run All Cells

Run the notebook from top to bottom. The notebook will:

1. load the dataset;
2. filter QA/test-related respondents;
3. clean selected variables;
4. calculate descriptive statistics;
5. calculate proxy-readiness categories;
6. generate tables and charts;
7. export processed outputs.

### Step 5: Download or Save Outputs

After running the notebook, download the generated CSV files, tables, and charts from the Colab file panel or save them to Google Drive.

## Requirements

The project uses the following Python packages:

```text
pandas
numpy
matplotlib
jupyter
openpyxl
```

These packages should also be included in `requirements.txt`.

## Academic Use Note

This project uses secondary public survey data. No primary data collection, interviews, questionnaires, or experiments were conducted.

The analysis is descriptive and proxy-based. The dataset does not directly measure manual testing background, automation competence, or workplace readiness. Therefore, the findings should be interpreted as an indirect readiness profile rather than a direct assessment of automation-testing ability.

## Limitations

The main limitation is that the Stack Overflow Developer Survey dataset does not directly identify manual testers or directly assess automation-testing competence.

The analysis depends on available survey variables and role/profile indicators. Therefore, the proxy-readiness score is useful for descriptive analysis, but it cannot prove actual automation skills or workplace performance.

## GitHub Upload Notes

Before uploading this repository to GitHub:

1. Remove duplicate file suffixes such as `(1)` and `(2)`.
2. Keep only the final version of each CSV file.
3. Extract any ZIP output folder before uploading.
4. Upload the `.ipynb` notebook used in Google Colab.
5. Upload generated charts and processed tables in organised folders.
6. Do not upload passwords, credentials, or private account details.
7. Do not upload copyrighted research paper PDFs to GitHub.
8. Share research paper PDFs or reference sources directly with the supervisor/client instead.

## Suggested GitHub Folder Upload Checklist


## Repository Purpose

This repository is prepared as a supporting project package for the dissertation analysis. It allows the professor, supervisor, or reviewer to understand how the dataset was filtered, how the proxy-readiness score was calculated, how the charts were generated, and how the main findings were produced.
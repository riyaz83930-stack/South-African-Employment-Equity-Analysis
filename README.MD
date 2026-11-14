# South African Employment Equity Data Analysis

## Project Overview

An end-to-end data analytics project analysing South African Employment Equity employer and workforce data across multiple reporting years.

The project focuses on inspecting data quality, cleaning and restructuring datasets, integrating employer metadata with workforce records, performing exploratory data analysis (EDA), and presenting workforce insights through an interactive Power BI dashboard.

The analysis explores demographic representation, gender distribution, occupational levels, industry distribution and provincial workforce patterns.

## Project Objectives

The project was designed to answer the following questions:

1. What structural and data-quality issues exist in the supplied datasets?
2. How should the employer metadata be restructured to support year-wise analysis?
3. Can employer metadata and workforce profile records be reliably integrated?
4. How are workforce counts distributed across demographic and gender groups?
5. How does workforce composition change across reporting years?
6. Which occupational levels account for the largest reported workforce?
7. How does demographic and gender representation vary across occupational levels?
8. Are there unusual workforce values that require further investigation?
9. How can the findings be communicated through an interactive dashboard?

## Repository Structure

```text
71point4 analyst assignment/
│
├── Outputs/
│   ├── ee_meta_clean
│   ├── ee_meta_final_long_format
│   └── ee_profile_clean
│
├── raw_data/
│   ├── ee_meta
│   └── ee_profile_all
│
├── Reports/
│   ├── Data Quality Reports
│   ├── Summary Tables
│   ├── Outlier Reports
│   └── Final_Analysis_Tables_EXCEL
│
├── visuals/
│   └── EDA Charts
│
├── Employment_Equity_Dashboards.pbix
├── stage_1_Cleaning_&_EDA.ipynb
├── README.md
└── Analysis_Report.md
```

## Dataset Description

### Employer Metadata — ee_meta.csv

Contains employer-level information such as:

- Employer reference ("Ee_Ref")
- Registration name
- Industry sector
- Business type
- Physical province
- Year-specific employer attributes

### Workforce Profile — ee_profile_all.csv

Contains workforce composition information such as:

- Employer reference
- Submission year
- Occupational level
- Workforce counts across five demographic groups and two gender categories

Demographic groups: African, Coloured, Foreign, Indian and White.

Gender categories: Female and Male.

## Methodology and Workflow

### 1. Data Inspection

- Examined dataset dimensions, column names and data types.
- Reviewed missing values, repeated employer references and numerical distributions.
- Inspected year-specific metadata columns.

### 2. Data Cleaning

- Standardised column names and text fields.
- Checked exact duplicate records.
- Checked missing and negative numerical values.
- Examined zero-value distributions.
- Investigated unusual workforce counts.

### 3. Metadata Restructuring

The employer metadata was originally stored in a wide format, with separate columns for attributes across reporting years.

The year-specific columns were transformed using Pandas "melt()". Reporting years and attribute names were extracted, and the data was pivoted into an employer-year structure.

The resulting metadata uses "Ee_Ref" and "year" as its employer-year identifiers.

### 4. Dataset Integration

The cleaned workforce profile was merged with restructured employer metadata using employer reference and reporting year.

A many-to-one merge validation was applied to check the relationship between the datasets and preserve workforce profile records.

### 5. Exploratory Data Analysis

The analysis included:

- Descriptive statistics
- Zero and non-zero workforce distribution
- IQR-based outlier detection
- Year-wise demographic workforce trends
- Occupational workforce aggregation
- Occupational demographic composition
- Gender-based workforce analysis

Summary tables and quality reports are stored in "Reports/". EDA charts are stored in "visuals/".

## Power BI Dashboard

The interactive dashboard contains four pages:

### 1. Workforce Overview

- Total workforce, employers, reporting years and occupation levels
- Year-wise workforce trend
- Occupation-wise workforce
- Gender distribution

### 2. Demographic & Gender Analysis

- Year-wise demographic workforce distribution
- Demographic-wise workforce
- Female and Male workforce
- Demographic composition over time

### 3. Occupational Analysis

- Management workforce and representation percentage
- Demographic composition by occupation
- Gender distribution by occupation
- Year-wise occupational workforce
- Occupational demographic and gender breakdown

### 4. Industry & Province Analysis

- Employers by business type
- Industry-wise workforce
- Industry-wise demographic composition
- Province-wise workforce
- Total employers, workforce and industries

Interactive slicers allow users to explore the data by reporting year, occupation, industry, province and business type, according to the selected page.

## Power BI Data Model

The model contains:

- "meta_final"
- "profile_final"
- "Dim_Year"
- "dim_occupation"
- "_measures"

The workforce profile was transformed into a demographic and gender-based structure to support flexible reporting.

Employer-year information is connected to workforce records, while year and occupation dimensions support filtering and analysis.

## Validation and Reconciliation

| Validation | Result |
| --- | --- |
| Cleaned workforce profile records | 42,000 |
| Records after metadata integration | 42,000 |
| Unmatched metadata records | 0 |
| Duplicate employer-year keys in metadata | 0 |
| Reporting period | 2013–2024 |
| Total reported workforce | 4,492,707 |

The total workforce aggregation was reconciled between Python and Power BI. Power BI displays the total in a rounded format.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- Power BI
- Power Query
- DAX

## How to Explore the Project

1. Review "stage_1_Cleaning_&_EDA.ipynb" for the Python workflow.
2. Explore cleaned datasets in "Outputs/".
3. Review quality reports and summary tables in "Reports/".
4. Explore the saved EDA charts in "visuals/".
5. Open "Employment_Equity_Dashboards.pbix" to explore the interactive dashboard.
6. Read "Analysis_Report.md" for the key findings, limitations, recommendations and conclusion.

## Interpretation Note

Workforce totals are aggregated reported counts across employers and reporting years. They should not be interpreted as unique individuals across the entire reporting period.

The analysis identifies observed patterns and does not independently establish the causes of demographic differences.

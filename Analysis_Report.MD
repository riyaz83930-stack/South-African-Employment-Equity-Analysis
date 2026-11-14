# Employment Equity Data Analysis

**Key Findings, Limitations & Recommendations**

## 1. Executive Summary

This analysis examined South African employer metadata and workforce composition data across 12 reporting years (2013–2024).

After cleaning, restructuring and integration, the workforce profile contained 42,000 records representing an aggregate reported workforce of 4,492,707.

The analysis identified substantial differences in demographic and gender representation, changes in workforce composition over time, concentration of reported workforce counts in particular occupational levels, and highly skewed workforce distributions.

## 2. Key Findings

### 2.1 Workforce Concentration Across Occupational Levels

The largest reported workforce counts were concentrated in skilled technical and semi-skilled occupational levels.

| Occupational Level | Reported Workforce |
| --- | ---: |
| Skilled Technical and related levels | 1,584,407 |
| Semi-Skilled | 1,246,323 |
| Unskilled | 594,006 |
| Temporary Employees | 560,969 |
| Professionally Qualified and Mid-Management | 373,516 |
| Senior Management | 60,900 |
| Temporary | 53,278 |
| Top Management | 19,308 |

**Finding:** Skilled Technical and Semi-Skilled categories together account for the largest share of the aggregated reported workforce. Senior and Top Management have considerably lower reported counts.

### 2.2 Changes in Demographic Representation

Selected demographic shares across reporting years:

| Demographic Group | 2013 | 2022 | 2024 |
| --- | ---: | ---: | ---: |
| African Female | 35.41% | 47.52% | 44.19% |
| African Male | 38.70% | 33.81% | 35.33% |
| White Female | 4.63% | 2.78% | 3.03% |
| White Male | 6.05% | 3.46% | 3.83% |

**Finding:** African Female representation increased between 2013 and 2022, followed by a lower reported share in 2024. White Female and White Male shares were also lower in 2024 than in 2013.

These are changes in reported composition, not necessarily changes in the number of unique employees.

### 2.3 Demographic and Gender Distribution

Zero-value analysis across 42,000 workforce records identified substantial differences between demographic groups.

| Group | Zero Records | Zero Percentage |
| --- | ---: | ---: |
| African Female | 23,120 | 55.05% |
| African Male | 20,192 | 48.08% |
| Coloured Female | 31,200 | 74.29% |
| Coloured Male | 29,771 | 70.88% |
| Foreign Female | 39,099 | 93.09% |
| Foreign Male | 36,154 | 86.08% |
| Indian Female | 34,621 | 82.43% |
| Indian Male | 33,254 | 79.18% |
| White Female | 26,056 | 62.04% |
| White Male | 21,052 | 50.12% |

**Finding:** Foreign Female and Foreign Male categories had particularly high zero-value percentages. African Male had the lowest zero percentage among the ten groups.

Zero values were retained because they may represent genuine absence of employees in a particular employer, year or occupational category.

### 2.4 Demographic Composition Within Occupational Levels

Selected workforce shares within occupational groups:

| Occupational Level | Notable Representation |
| --- | --- |
| Skilled Technical | African Female: 45.88% |
| Semi-Skilled | African Male: 47.14% |
| Unskilled | African Male: 57.38% |
| Temporary Employees | African Female: 60.73% |
| Professionally Qualified and Mid-Management | African Female: 25.05% |
| Senior Management | White Male: 35.71% |
| Top Management | White Male: 51.70% |

**Finding:** Demographic composition varies considerably across occupational levels. White Male representation is particularly notable in the Top Management category, while African Female and African Male groups have higher shares in several other occupational categories.

These differences describe the observed workforce composition; they do not establish discrimination or its causes.

### 2.5 Outlier and Distribution Analysis

The descriptive statistics and boxplots showed highly skewed workforce distributions.

Examples of maximum reported counts in individual records:

| Group | Maximum |
| --- | ---: |
| African Female | 73,872 |
| African Male | 22,317 |
| Indian Female | 5,941 |
| Indian Male | 2,280 |
| White Female | 2,385 |
| White Male | 543 |

Some demographic columns had an IQR of zero because their 25th and 75th percentiles were zero. This caused many positive observations to be flagged as outliers.

Further investigation of employer "Aaf824B8B" showed the following Indian Male counts at the Skilled Technical level:

| Year | Workforce |
| --- | ---: |
| 2013 | 2,280 |
| 2014 | 2,254 |
| 2015 | 2,187 |
| 2016 | 2,039 |
| 2017 | 1,944 |

**Finding:** The values showed a declining pattern across these years. They were retained because the investigation did not establish that they were data errors.

This demonstrates that statistical outlier flags require contextual review before any records are removed.

### 2.6 Industry and Provincial Distribution

The Power BI dashboard provides interactive analysis of:

- Industry-wise workforce
- Province-wise workforce
- Employer distribution by business type
- Industry-wise demographic composition

The dashboard shows that workforce totals vary across industries and provinces. KwaZulu-Natal and Gauteng are the two largest provincial workforce categories in the displayed overview.

## 3. Data Validation and Reconciliation

| Validation | Result |
| --- | --- |
| Workforce profile records | 42,000 |
| Records after metadata integration | 42,000 |
| Unmatched metadata records | 0 |
| Duplicate employer-year metadata keys | 0 |
| Python total workforce | 4,492,707 |
| Power BI total workforce | Approximately 4.49M |

**Finding:** The merged record count remained unchanged, metadata matching was complete for the inspected workforce records, and the Python workforce total reconciled with the rounded Power BI value.

## 4. Limitations

1. The data represents employer-reported workforce counts and may be affected by reporting coverage and consistency.
2. Aggregated counts across multiple years do not represent unique individuals.
3. Changes in employer participation may influence year-wise comparisons.
4. IQR-based outlier detection is less informative for columns with zero-valued quartiles.
5. Zero values cannot automatically be interpreted as missing or incorrect data.
6. The categories "Temporary" and "Temporary Employees" were retained separately because their equivalence was not established.
7. Demographic differences across occupational levels do not independently prove discrimination or explain its causes.
8. Industry and provincial comparisons should be interpreted in the context of employer coverage and reported workforce size.

## 5. Recommendations

- Monitor demographic and gender representation across occupational levels and reporting years.
- Review senior and top management representation in greater detail.
- Investigate unusually high workforce counts using employer and year context before changing records.
- Maintain zero values where they represent genuine workforce absence.
- Improve consistency in occupational category labels, particularly temporary-related categories.
- Review employer participation and reporting coverage before drawing conclusions from year-wise changes.
- Use the interactive dashboard to identify groups, industries and provinces that require further investigation.

## 6. Conclusion

The analysis successfully integrated employer metadata with workforce profile records and produced a consistent analytical dataset containing 42,000 workforce records.

The findings highlight workforce concentration in skilled technical and semi-skilled occupational levels, changes in demographic composition over time, and differences in demographic representation across occupational categories.

The investigation also demonstrated that unusual workforce counts are not automatically data errors and that zero values can carry meaningful information.

The final Power BI dashboard makes these patterns explorable across reporting years, demographic groups, occupations, industries, provinces and business types.

Overall, the project provides a structured view of reported Employment Equity workforce patterns while identifying areas where further investigation and improved reporting consistency could add value.

# US COVID-19 Outbreak and Progression

**Author:** Cynthia Wang  
**Date:** December 2025  
**Language:** R (R Markdown)

---

## Overview

This project reconstructs the comprehensive trajectory of the COVID-19 pandemic in the United States from **January 21, 2020 through March 23, 2023**. Using data from the New York Times and U.S. Census Bureau, the analysis quantifies the aggregate public health burden, characterizes seasonal wave patterns, and evaluates geographic heterogeneity across U.S. states and territories.

---

## Repository Structure

```
us-covid19-analysis/
│
├── US_COVID19_Analysis.Rmd      # Main analysis file (R Markdown)
│
├── data/
│   └── raw/                     # Raw input data (included in repository)
│       ├── us.csv
│       ├── us-states.csv
│       ├── us-population.xlsx
│       └── islands-population.xlsx
│
├── output/
│   └── figures/                 # Generated plots (auto-created on render)
│
├── docs/                        # Additional documentation
│
├── .gitignore
└── README.md
```

---

## Data Sources

| Dataset | Source | Description |
|---|---|---|
| `us.csv` | [NYT GitHub](https://github.com/nytimes/covid-19-data) | National cumulative cases & deaths |
| `us-states.csv` | [NYT GitHub](https://github.com/nytimes/covid-19-data) | State-level cumulative cases & deaths |
| `us-population.xlsx` | [U.S. Census Bureau](https://www.census.gov/data/tables/time-series/demo/popest/2020s-state-total.html) | Annual population estimates for 51 states |
| `islands-population.xlsx` | [IDB](https://www.census.gov/data-tools/demo/idb/) | Population for Guam, Virgin Islands, American Samoa, N. Mariana Islands |

> **Note:** All raw data files are included in the `data/raw/` folder for full reproducibility. Original sources are linked above for reference.

---

## Requirements

### R Version
R 4.0 or higher recommended.

### Packages

```r
install.packages(c(
  "tidyverse",   # Data manipulation & visualization
  "magrittr",    # Pipe operator
  "readxl",      # Excel file reading
  "lubridate",   # Date handling
  "stringr",     # String manipulation
  "zoo",         # Rolling mean
  "patchwork",   # Combining plots
  "usmap",       # U.S. map visualization
  "scales",      # Number formatting
  "tidytext"     # Reordering within facets
))
```

---

## How to Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/us-covid19-analysis.git
   cd us-covid19-analysis
   ```

2. **Render the report** in RStudio:
   - Open `US_COVID19_Analysis.Rmd`
   - Click **Knit** (or run `rmarkdown::render("US_COVID19_Analysis.Rmd")`)

3. The output PDF will be generated in the project root directory, and all figures will be saved to `output/figures/`.

---

## Key Analysis Sections

| Section | Description |
|---|---|
| **Data Preparation** | Importing, cleaning, joining, and tidying all datasets |
| **Overall U.S. Impact** | Cumulative totals, per-capita rates, case fatality rate |
| **State Rankings** | Top 10 states by absolute and per-capita impact |
| **Geographic Maps** | Choropleth maps of cases and deaths across U.S. states |
| **Temporal Evolution** | Cumulative trends with variant milestones annotated |
| **Monthly Patterns** | Wave identification and seasonality analysis |
| **Rolling Averages** | 30-day rolling average trends for severely impacted states |

---

## Key Findings

- **103.9 million** total cases and **1.1 million** total deaths recorded through March 2023.
- Five distinct pandemic waves identified, with the **Omicron surge (Jan 2022)** producing the highest case counts.
- Clear **decoupling of cases and deaths** after Omicron, consistent with vaccination and natural immunity effects.
- **Regional seasonality:** Southern states (AZ, FL, TX) peaked in summer; Northern states (NY, RI) peaked in winter.
- Per-capita analysis highlights disproportionate impact in smaller states: **Alaska, Rhode Island, West Virginia**.

---

## Limitations

- Early testing shortages likely undercount infections, particularly in New York in early 2020.
- Vaccination coverage data were not integrated, limiting causal inference about fatality rate decline over time.
- Analysis ends in March 2023 and does not capture post-study variant developments.

---

## License

This project is for educational and research purposes. COVID-19 data is sourced from the New York Times and is subject to their [data use terms](https://github.com/nytimes/covid-19-data/blob/master/LICENSE).

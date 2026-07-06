# Road Accidents in India (2021–2024)

## Project Overview

This project analyzes official State/UT-level road accident data for India from 2021 to 2024.

The objective is to build a complete data analytics portfolio project covering:

- Data cleaning and validation
- Exploratory data analysis
- Comparison of absolute and normalized accident indicators
- Trend analysis
- Power BI dashboard development
- Insight generation and storytelling

A major analytical focus of the project is that raw accident counts alone can be misleading. States with larger populations or more vehicles may report more accidents, so accident rates per lakh population, registered vehicles and road length should also be considered.

## Data Source

**Source:** Ministry of Road Transport and Highways, Government of India  
**Report:** *Road Accidents in India 2024*

The original dataset contains:

- 36 States and Union Territories
- Road accident counts from 2021 to 2024
- 2024 accident ranking
- Percentage share of national accidents
- Accidents per lakh population
- Accidents per 10,000 registered vehicles
- Accidents per 10,000 km of roads

## Project Structure

```text
road-accidents-india-analysis/
├── data/
│   ├── raw/
│   │   ├── datafile.xls
│   │   └── datafile_converted.xlsx
│   └── processed/
│       ├── accidents_cleaned.csv
│       ├── accidents_trend_long.csv
│       └── national_totals.csv
├── notebooks/
│   └── 01_data_cleaning.ipynb
├── dashboard/
├── images/
├── references/
├── README.md
├── requirements.txt
└── .gitignore



## Progress Log

### Day 1 — Data Cleaning and Validation

Completed the following tasks:

- Preserved the original `.xls` source file
- Converted the legacy Excel file into `.xlsx` format for reliable processing
- Loaded and inspected the raw dataset using Pandas
- Renamed 17 verbose columns into analysis-ready `snake_case` names
- Separated the national `Total` row from State/UT-level records
- Converted count, rank, and rate columns into suitable numeric data types
- Retained Ladakh's unavailable vehicle-normalized accident rate as a missing value
- Added a flag showing whether the vehicle-rate value is available
- Calculated the 2023–2024 year-over-year percentage change
- Calculated the 2021–2024 compound annual growth rate
- Added a custom analytical region grouping
- Reshaped the four yearly accident columns into a long-format trend table
- Validated all yearly State/UT totals against the reported national totals
- Exported analysis-ready CSV files

## Validation Results

| Year | Calculated State/UT Total | Reported National Total | Difference |
|---:|---:|---:|---:|
| 2021 | 412,432 | 412,432 | 0 |
| 2022 | 461,312 | 461,312 | 0 |
| 2023 | 480,583 | 480,583 | 0 |
| 2024 | 487,707 | 487,707 | 0 |

All four yearly totals matched the national figures reported in the source dataset.

## Processed Datasets

### `accidents_cleaned.csv`

State/UT-level analysis table containing:

- Accident counts from 2021 to 2024
- Percentage shares
- Population-normalized rates
- Vehicle and road-normalized rates
- 2024 ranking
- Year-over-year change
- Four-year CAGR
- Region grouping
- Missing-data availability flag

**Shape:** 36 rows × 21 columns

### `accidents_trend_long.csv`

Long-format dataset designed for:

- Time-series analysis
- Line charts
- Power BI year filters
- State/UT trend comparisons

**Shape:** 144 rows × 5 columns

### `national_totals.csv`

The original national `Total` row retained separately for validation.

**Shape:** 1 row × 17 columns

## Missing-Value Decision

The accident rate per 10,000 vehicles was unavailable for Ladakh.

The value was retained as missing instead of being imputed because estimating it could distort normalized rankings and comparisons.

## Tech Stack

- Python
- Pandas
- NumPy
- Jupyter Notebook
- VS Code
- Excel
- Git and GitHub
- Power BI

## Next Steps

### Day 2 — Exploratory Data Analysis and Dashboard

- Compare rankings by raw accident count and accident rate per lakh population
- Identify States/UTs with the largest increases and decreases
- Analyze regional differences
- Find unusual State/UT patterns
- Build an interactive Power BI dashboard











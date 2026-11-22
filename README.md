# Data Science Jobs Cleaning & EDA

A data wrangling and exploratory data analysis (EDA) pipeline built to transform a raw, scraped Glassdoor job market dataset (`Uncleaned_DS_jobs.csv`) into structured, analysis-ready data.

## Overview
Scraped job board data is full of formatting artifacts, masked nulls (`-1`), and concatenated strings that prevent direct analysis. This project automates the cleaning, parsing, and feature engineering process to uncover baseline salary trends and industry compensation patterns across data science roles.

## Key Steps
* **Data Cleaning & Standardization:** Replaced `-1` and `"Unknown"` placeholders with proper nulls, standardized column names to snake_case, and stripped newline characters (`\n`) and embedded ratings from company names and job descriptions.
* **Salary & Revenue Parsing:** Extracted min/max bounds from salary strings (e.g., `"$137K-$171K"`) into numerical midpoints (`salary_num`), and built a regex parser to convert unstructured revenue ranges into continuous numeric values (`revenue_num`).
* **Feature Engineering:** Classified job seniority (`junior`, `senior`, `lead`, `unspecified`) using keyword extraction from job titles/descriptions and computed average employee headcount (`size_num`).
* **Exploratory Data Analysis:** Analyzed overall salary distributions and aggregated compensation across industries using histograms, KDE plots, boxplots, and bar charts.

## Key Takeaways
* **Salary Distribution:** Estimated salaries follow a roughly normal distribution centered around the **$110K–$130K** range, with a few high-paying outliers pushing above $200K.
* **Top-Paying Industries:** Sectors like **Biotech & Pharmaceuticals**, **Information Technology**, and **Finance** consistently offer the highest average compensation for data science talent.
* **Data Quality Impact:** Properly parsing hidden null markers (`-1`) and separating concatenated fields significantly reduces bias when aggregating company size and revenue metrics.

## Tech Stack
* **Python 3**
* **Pandas & NumPy** — Data manipulation and feature engineering
* **Regex (`re`)** — Text parsing and string extraction
* **Matplotlib & Seaborn** — Statistical data visualization


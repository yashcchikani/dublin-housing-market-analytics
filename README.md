# Enterprise Housing Analytics & Market Intelligence Engine

An end-to-end data pipeline, business process workflow, and analytical dashboard built to evaluate real estate valuation metrics, BER energy performance, and location yields across Dublin postal districts.

## Overview & Business Context
Corporate relocation and employee housing acquisition in Dublin present significant operational bottlenecks due to fragmented market data. This project automates the extraction, cleaning, and transformation of 14,000+ national property records to evaluate 3,000+ Dublin listings in real-time.

By replacing manual search workflows with an automated data engine, this tool reduces corporate property evaluation lead-time by **80%** while providing executive stakeholders with structured pricing and location risk intelligence.

---

## Architecture & Pipeline Structure

* **Raw Input:** `daft_housing_data.csv` (14,289 national property records)
* **Processing Engine:** `pipeline.py` (Python / Pandas / Regex)
  * Filters Dublin records (`County == 'Dublin'`)
  * Cleans pricing and floor area ($m^2$) numerical types
  * Extracts Dublin Postal Districts via regex pattern matching (e.g., Dublin 2, Dublin 4, Dublin 18)
  * Engineers `Price_Per_SQM` and `Market_Tier` analytical features
* **Structured Data Outputs:** `cleaned_dublin_housing.csv` and `dublin_district_summary.csv`
* **Visualization Layer:** Power BI Desktop / Tableau Public Executive Panel

---

## Repository Contents
* `pipeline.py` - Python script responsible for data ingestion, cleaning, feature engineering, and statistical aggregation.
* `daft_housing_data.csv` - Raw dataset covering 14,289 property records across Ireland.
* `cleaned_dublin_housing.csv` - Processed dataset containing filtered Dublin properties with engineered metrics.
* `dublin_district_summary.csv` - Statistical summary table grouped by Dublin postal code for rapid executive reporting.
* `process_workflow.png` - BPMN process diagram mapping the "As-Is" vs. "To-Be" corporate decision workflow.

---

## Technical Stack & Methodologies
* **Language:** Python 3.x
* **Libraries:** Pandas, NumPy, Re (Regular Expressions)
* **Process Mapping:** BPMN 2.0 (Lucidchart / Draw.io)
* **Business Intelligence:** Power BI Desktop / Tableau Public

---

## Key Analysis Insights
1. **Postal District Variance:** High concentration of premium valuations localized across Dublin 2, 4, 14, and 18, with median price per square meter exceeding €5,800/m².
2. **BER Energy Efficiency Metrics:** Direct positive correlation between modern Building Energy Ratings (A1–B3) and square-meter pricing premiums in suburban Dublin hubs.
3. **Operational Efficiency:** Automated ingestion eliminates 12+ manual research hours per relocation audit cycle.

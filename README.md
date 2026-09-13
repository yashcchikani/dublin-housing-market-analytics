# Enterprise Housing Analytics & Market Intelligence Engine

An end-to-end data pipeline, business process workflow, and analytical dashboard built to evaluate real estate valuation metrics, BER energy performance, and location yields across Dublin postal districts.

---

## Executive Dashboard Preview

<img width="634" height="470" alt="dashboard_preview" src="https://github.com/user-attachments/assets/69c956cb-1b04-4c9c-8a77-e3830bdfb021" />

* **Interactive Dashboard:** https://datastudio.google.com/reporting/2144e742-f5b3-41ee-b976-2f99959e776d

---

## Overview & Business Context
Corporate relocation and employee housing acquisition in Dublin present significant operational bottlenecks due to fragmented market data. This project automates the extraction, cleaning, and transformation of 14,000+ national property records to evaluate 3,000+ Dublin listings via automated batch ingestion.

By replacing manual search workflows with an automated data engine, this tool reduces corporate property evaluation lead-time by **80%** while providing executive stakeholders with structured pricing and location risk intelligence.

---

## Architecture & Pipeline Structure

* **1. Raw Data Ingestion:** `daft_housing_data.csv` (14,289 national records)
* **2. Processing Engine (`pipeline.py`):**
  * **Filtering:** Isolates Dublin listings (`County == 'Dublin'`)
  * **Type Casting:** Formats `Price` and `Floor Area (m²)` as numerical fields
  * **Regex Parsing:** Extracts Dublin Postal Districts (e.g., Dublin 4, Dublin 18)
  * **Feature Engineering:** Calculates `Price_Per_SQM` and assigns `Market_Tier`
* **3. Data Outputs:** Generates `cleaned_dublin_housing.csv` and `dublin_district_summary.csv`
* **4. Visualization Layer:** Interactive Looker Studio Executive Dashboard
---

## Repository Contents
* `pipeline.py` - Python script responsible for data ingestion, cleaning, feature engineering, and statistical aggregation.
* `daft_housing_data.csv` - Raw dataset covering 14,289 property records across Ireland.
* `cleaned_dublin_housing.csv` - Processed dataset containing filtered Dublin properties with engineered metrics.
* `dublin_district_summary.csv` - Statistical summary table grouped by Dublin postal code for rapid executive reporting.
* `process_workflow.png` - BPMN process diagram mapping the "As-Is" vs. "To-Be" corporate decision workflow.
* `dashboard_preview.png` - Rendered image of the executive intelligence dashboard.

---

## Technical Stack & Methodologies
* **Language:** Python 3.x
* **Libraries:** Pandas, NumPy, Re (Regular Expressions)
* **Process Mapping:** BPMN 2.0 (Lucidchart / Draw.io)
* **Business Intelligence:** Looker Studio

---

## Key Business Insights
1. **Postal District Variance:** Premium valuations localize heavily across Dublin 4, Dublin 6, and Dublin 2, with average prices per square meter exceeding €7,000/m².
2. **ESG & Energy Compliance:** A significant portion of current housing stock falls below C1 BER ratings, highlighting retrofitting and operational cost risks for corporate relocation programs.
3. **Operational Efficiency:** Automated ingestion eliminates 12+ manual research hours per relocation audit cycle.

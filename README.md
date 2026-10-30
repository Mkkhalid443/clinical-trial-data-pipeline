# Clinical Trial Data Pipeline | Databricks

## Project Overview

This project demonstrates an end-to-end clinical trial
data engineering and analytics workflow.

## Technologies Used

- Databricks
- Python
- SQL
- Apache Spark
- Delta Lake
- Medallion Architecture

## Key Performance Indicators

| Metric | Result |
|---|---:|
| Total Clinical Trials | 1,000 |
| Total Reported Enrollment | 779,828 |
| Average Enrollment per Trial | Approximately 790 |
## Clinical Trial Analytics Dashboard

This interactive Databricks dashboard analyzes 1,000 clinical trials retrieved from ClinicalTrials.gov.

The dashboard includes:
- Total clinical trials: 1,000
- Total reported enrollment: 779,828
- Average enrollment per trial: approximately 790
- Recruitment status distribution
- Clinical trial phases
- Medical condition analysis

### Dashboard Preview

![Clinical Trial Analytics Dashboard](https://raw.githubusercontent.com/Mkkhalid443/clinical-trial-data-pipeline/main/%20%20%20%20clinical-trial-dashboard.png)

### Data Architecture

This project uses the Medallion Architecture to organize clinical trial data into three layers: Bronze, Silver, and Gold.

The architecture separates raw data ingestion, data cleaning, and analytical processing to support reliable reporting and data analysis.

### Bronze Layer: Raw Data Ingestion

The Bronze layer stores raw clinical trial records retrieved from the ClinicalTrials.gov API.

The data includes study identifiers, recruitment status, enrollment information, study phases, and medical conditions.

Purpose: Preserve source data before transformation.

### Silver Layer: Data Cleaning and Transformation

The Silver layer transforms raw clinical trial records into structured datasets suitable for analysis.

Processing includes:

* Extracting relevant clinical trial attributes.
* Organizing data into structured columns.
* Preparing recruitment and enrollment information.
* Checking data completeness and consistency.
* Storing processed records in a Delta table.

Purpose: Create a consistent dataset that can support downstream analytics.

### Gold Layer: Analytical Aggregation

The Gold layer prepares clinical trial data for reporting and visualization.

The analytical datasets support:

* Clinical trial counts by recruitment status.
* Enrollment analysis.
* Study phase distributions.
* Medical condition comparisons.
* Clinical trial trends over time.

Purpose: Transform processed clinical trial data into information that stakeholders can use to understand research activity.

### Data Flow

ClinicalTrials.gov API → Bronze Layer → Silver Layer → Gold Layer → Databricks AI/BI Dashboard

This layered approach demonstrates how clinical research data can move from publicly available records to structured analytical datasets and interactive visualizations.

## Data Pipeline Architecture

This project implements a three-layer Medallion Architecture using Databricks, Apache Spark, SQL, and Delta Lake.

```mermaid
flowchart TD
    A["ClinicalTrials.gov API<br/>1,000 Clinical Trials"]
    B["BRONZE LAYER<br/>Raw Clinical Trial Data<br/>clinical_trials_bronze"]
    C["SILVER LAYER<br/>Data Cleaning & Validation<br/>clinical_trials_silver"]
    D["GOLD LAYER<br/>Analytical Aggregations"]
    E["Recruitment Status<br/>clinical_trials_gold_status"]
    F["Study Phase<br/>clinical_trials_gold_phase"]
    G["Medical Conditions<br/>clinical_trials_gold_condition"]
    H["Databricks Analytics Dashboard<br/>KPIs, Charts & Filters"]

    A --> B
    B --> C
    C --> D
    D --> E
    D --> F
    D --> G
    E --> H
    F --> H
    G --> H

    style A fill:#e8eaf6,stroke:#3949ab,color:#1a237e
    style B fill:#fff3e0,stroke:#ef6c00,color:#5d4037
    style C fill:#eceff1,stroke:#607d8b,color:#263238
    style D fill:#fff8e1,stroke:#f9a825,color:#5d4037
    style E fill:#e8f5e9,stroke:#388e3c,color:#1b5e20
    style F fill:#e8f5e9,stroke:#388e3c,color:#1b5e20
    style G fill:#e8f5e9,stroke:#388e3c,color:#1b5e20
    style H fill:#e0f7fa,stroke:#00838f,color:#006064
```

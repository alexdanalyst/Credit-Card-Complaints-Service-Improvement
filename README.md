# Credit Card Complaints Analytics & AI-Assisted Service Improvement
> *Analyzed 86,893 credit card complaint records to investigate complaint patterns, company response performance, and opportunities to improve customer service through data-driven decisions and AI-assisted workflow automation.*
---
## ⚙️ Project Type Flags
> 
- [x] Exploratory Data Analysis (EDA)
- [x] SQL Analysis / Querying
- [x] Dashboard / Data Visualization
- [x] Data Pipeline / ETL
- [ ] Predictive Modelling / Machine Learning
- [x] Data Cleaning / Wrangling
- [x] End-to-End (multiple of the above)
- [x] Other: Business Process Analysis & AI Automation Design
---
## Table of Contents
1. [Project Overview](#1-project-overview)
2. [Objectives](#2-objectives)
3. [Project Scope & Tools](#3-project-scope--tools)
4. [Repository Structure](#4-repository-structure)
5. [Data Workflow](#5-data-workflow)
6. [Data Model & Schema](#6-data-model--schema)
7. [Analysis & Metrics](#8-analysis--metrics)
8. [Key Insights](#9-key-insights)
9. [Recommendations](#10-recommendations)
10. [Assumptions & Limitations](#11-assumptions--limitations)
11. [Future Enhancements](#12-future-enhancements)
12. [Deliverables](#13-deliverables)
13. [Author](#14-author)

---
## 1. Project Overview
**Context:**  Financial institutions receive customer complaints about billing disputes, interest rates, fraud, fees, account closures, and other credit card issues. Understanding these complaints can help organizations identify recurring service problems and improve how they respond to customers.

**Problem Statement:** How can complaint data be used to identify major sources of customer dissatisfaction, evaluate response timeliness, compare company performance fairly, and identify opportunities to streamline complaint handling?

**Approach:** This project will profile and clean a credit card complaints dataset, use SQL to investigate complaint patterns and response outcomes, and build a Power BI dashboard to communicate the findings. It will also map a proposed AI-assisted complaint-handling workflow, including classification, routing, validation, and human oversight.

**Outcome:** The planned deliverables are a reproducible analytical workflow, documented SQL queries, a Power BI dashboard, evidence-based business recommendations, and an AI automation prototype or documented workflow design. Final findings and any automation performance claims will be added after validation and testing.

## 2. Objectives

- **Primary Objective:** Identify the complaint categories and response-performance patterns that offer the clearest opportunities for customer-service improvement.

- **Secondary Objective 1:** Clean and validate the dataset, document data-quality issues, and prepare a reliable analytical dataset.

- **Secondary Objective 2:** Measure complaint volume, response timeliness, response outcomes, and differences across companies, complaint categories, submission channels, and time periods.

- **Secondary Objective 3:** Design and evaluate an AI-assisted workflow that could classify incoming complaints and recommend routing to the appropriate service team.
---
## 3. Project Scope & Tools

### Scope

| Dimension | Details |
|---|---|
| **In Scope** | Credit card complaint records, complaint categories, company responses, submission channels, dates, states, and available timeliness indicators |
| **Out of Scope** |Actual bank internal processes, individual customer investigations, private customer identification, and unsupported conclusions about the causes of complaints|
| **Time Period** | December 1, 2015 – April 10, 2021 |
| **Granularity** | Transaction-level summaries and itemized expense records |
| **Business Focus** |Customer service performance, complaint trends, data quality, process improvement, and AI-assisted workflow design|

### Tools & Technologies

| Category | Tool(s) Used |  Used |
|---|---|---|
| Data Storage | Excel/XLSX, CSV; SQL database if needed|Excel/XLSX, CSV; SQL database if needed|
| Data Processing | Excel, Power Query|
| Analysis | SQL |
| Visualization | Power BI, DAX|
| Version Control | Git and GitHub |
| Documentation | Markdown |
|AI Automation| LLM-based classification workflow, subject to implementation |
| Other | Data modelling and financial metric validation |

*These are the planned tools. The final table will list only technologies actually used.*
---

## 4. Repository Structure

```text
credit-card-complaints-analytics/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── queries/
│   ├── exploratory/
│   ├── transformations/
│   └── final/
│
├── power-query/
│
├── power-bi/
│   ├── dashboard/
│   └── measures/
│
├── automation/
│   ├── workflow-design/
│   ├── prompts/
│   └── evaluation/
│
├── docs/
│   ├── data-dictionary.md
│   ├── data-quality-report.md
│   └── process-map.md
│
├── visuals/
│
├── reports/
│
└── README.md
```

---
## 5. Data Workflow

```text
Data Workflow

Source Excel Workbook
        ↓
Data Profiling & Validation
        ↓
Cleaning and Transformation
        ↓
SQL Analysis and Metric Calculation
        ↓
Power BI Dashboard
        ↓
Business Recommendations
        ↓
AI-Assisted Workflow Prototype
        ↓
Testing, Documentation & Publication
```
### 1. Source
An Excel workbook containing 86,893 credit card complaint records and 25 columns.

### 2. Ingestion
Inspect the workbook, confirm the schema, check data types, and import the source into the chosen analysis environment.
Assign clear query names and inspect the columns, data types, and relationships before loading the data model.

### 3. Cleaning
Investigate missing values, date consistency, category naming, duplicate records, and the validity of response-time measurements. Document every material change.

### 4. Transformation
Create validated reporting fields, such as complaint month and year, response-duration measures where appropriate, and standardized category labels.

### 5. Analysis
Use SQL to investigate complaint volume, response timeliness, response outcomes, company differences, complaint categories, and submission channels.

### 6. Output
Produce a Power BI dashboard, reusable SQL queries, a data-quality report, business recommendations, and a documented AI-assisted workflow.
---

## 6. Data Model & Schema
### Dataset: credit_card_complaints

The source workbook contains a flat table with 25 columns. The initial schema includes the following fields:
**Row count:** 24

| Field Name | Data Type | Description |
|---|---|---|
| Complaint ID | Integer-like identifier | Identifier associated with a complaint |
| Company | Text |Financial company named in the record |
| Complaint Category | Text | Complaint category; the source column name contains trailing whitespace |
| Issue | Text | Issue classification recorded in the dataset |
| Date received | Date | Date the complaint was received |
|Date sent to company2 | Text | Date the complaint was sent to the company|
|Company response to consumer|Text| Recorded company response outcome |
| Timely response? |Text|Source-provided response-timeliness label|
|Submitted via|Text|Channel used to submit the complaint|
|Consumer disputed?|Text|Source-provided indicator of whether the consumer disputed the response|
|State|Text|State associated with the complaint|
|Consumer complaint narrative |Text|Consumer's written description, where available|
| Avg No of days  |Numeric| Explanation of an identified issue | Source-provided duration field; definition and validity require verification|

The workbook also contains fields such as Product, Dimension, Sub-issue, Sub-product, Tags, ZIP code, and Company public response.

Approximate row count: 86,893.

Date range: December 1, 2015 – April 10, 2021.

Key identifier: Complaint ID, subject to uniqueness validation.

Relationships: The initial analysis will use a single complaint table. Additional dimension tables will only be created if they improve the analytical model.

The data dictionary will be expanded to cover all source columns, their types, definitions, missing-value patterns, and cleaning decisions.

## 7. Analysis & Metrics

### Analytical Approach

The analysis will combine data profiling, descriptive analysis, comparisons across business dimensions, and time-based trend analysis.

SQL will be used to make the calculations reproducible. Power BI will present the validated results in an interactive format. The analysis will distinguish between observed associations and proven causes.

### Key Metrics Defined

| Metric | Plain-Language Definition | Why It Matters |
|---|---|---|
| Total Complaints | Count of valid, unique complaint records | Establishes the volume of recorded incoming funds |
|Timely Response Rate|Complaints labelled as receiving a timely response divided by complaints with a valid timeliness label|Measures recorded compliance with response-timeliness expectations|
|Untimely Response Count|Number of complaints labelled as receiving an untimely response|Identifies cases that may require service-process investigation|
|Response Outcome Distribution|Count and percentage of complaints by recorded company response outcome|Shows how recorded complaint outcomes are distributed|
|Complaint Category Share|Complaints in a category divided by all valid complaints| Identifies categories contributing the largest complaint volumes|
|Average Response Duration|Average validated elapsed time between appropriate date fields|Helps investigate processing delays, subject to date and duration validation|
|Complaint Trend|Complaint counts grouped by month or year|Identifies changes in recorded complaint volume over time|
|Company Complaint Share|A company's complaint count divided by the total in the selected comparison population|Supports comparisons of complaint volume while accounting for differences in the comparison period|

### Methods Used

- Data profiling and missing-value analysis.
- Duplicate and identifier validation.
- SQL aggregation, filtering, grouping, joins where justified, and window functions where useful.
- Trend analysis by month and year.
- Segmentation by company, issue, response outcome, state, and submission channel.
- Validation of response-duration fields against available dates.
- Power BI measures, interactive filters, and comparative visualizations.
- Process mapping and evaluation of a proposed AI-assisted workflow.

---

## 8. Key Insights
To be completed after the analytical queries and dashboard have been validated.

**Insight 1: Complaint concentration**
Identify the categories contributing the largest share of complaints and determine which issues deserve further operational investigation.

**Insight 2: Response timeliness**
Quantify timely and untimely responses, investigate how they vary across relevant groups, and validate whether the source labels support the intended interpretation.

**Insight 3: Company-level differences**
Compare complaint volumes and response patterns across companies, accounting for the available time period and limitations in the dataset.

**Insight 4: Trends over time**
Determine whether recorded complaint volumes and response outcomes changed across the period covered by the data.

**Insight 5: Data-quality implications**
Document how missing narratives, absent subcategories, incomplete fields, and questionable duration values affect the conclusions that can be drawn.
Each final insight will include a verified figure, the relevant comparison, its business implication, and any important qualification.

---

## 9. Recommendations

| Priority | Recommendation | Evidence Required | Suggested Owner |
|---|---|---|---|
| High | Investigate the complaint categories with the highest verified volumes | Category-level complaint analysis |Customer Service / Operations|
| High |Review the handling of complaints labelled as untimely|Validated timeliness analysis and case-level review|Service Operations / Compliance|
| Medium |Standardize complaint data collection and required fields |Data-quality assessment|Data Governance / Operations|
| Medium | Pilot AI-assisted complaint categorization and routing|Workflow test results and classification evaluation|Customer Service / Automation Team|
| Low | Establish recurring complaint-performance reporting|Validated dashboard and agreed KPI definitions|Business Intelligence / Operations|

Recommendations will be prioritized according to the magnitude of the verified issue, feasibility, business risk, and expected benefit.
---

## 10. Assumptions & Limitations

### Assumptions

- Each valid complaint record represents one complaint for counting purposes.
- Source-provided response labels are used as recorded until their definitions and reliability have been assessed.
- Missing values are not automatically interpreted as negative responses or as evidence of a particular customer outcome.
- Transaction dates represent the dates associated with the recorded financial activity.
- Comparisons between companies are descriptive unless appropriate exposure or business-volume data is available.

### Limitations
-The dataset covers a historical period ending April 10, 2021; it cannot establish current complaint patterns.
- Complaint counts alone do not measure the overall quality of a company because customer numbers and transaction volumes are not provided.
- Complaint narratives are missing for many records, limiting text analysis.
- Some source fields are entirely empty or substantially incomplete and may not support useful analysis.
- The source-provided duration field requires validation. Its observed values include negative values and extreme outliers, so it should not be used without investigation.
- Associations between complaint categories, companies, and outcomes do not establish causation.
- An AI workflow designed from this dataset cannot be assumed to improve service performance without testing against an appropriate evaluation set.

---

## 11. Future Enhancements

- [ ] Connect a recurring complaint export to an automated data-cleaning and reporting pipeline.
- [ ] Test AI-assisted complaint classification against manually reviewed labels.
- [ ] Add human approval, confidence thresholds, and exception handling to the proposed routing workflow.
- [ ] Evaluate processing time, classification errors, and routing accuracy before making automation-benefit claims.
- [ ] Incorporate additional business-volume data to support fairer comparisons of complaint rates.
- [ ] Refresh the analysis with more recent data if an appropriate source becomes available.

---

## 12. Deliverables

| Deliverable | Description | Location |
|---|---|---|
|Data Quality Report | Missing values, duplicates, anomalies, and cleaning decisions |docs/data-quality-report.md|
| Data Dictionary| Field definitions, data types, and source notes|docs/data-dictionary.md|
| Data Dictionary | Field definitions and table descriptions |`docs/data_dictionary.md` |
|SQL Analysis|Reproducible queries for profiling and business analysis|queries/|
|Power BI Dashboard|Interactive complaint and response-performance reporting|power-bi/|
|Business Findings Report|Verified insights and prioritized recommendations| reports/ |
|Process Map|Proposed complaint-handling workflow and improvement opportunities|docs/process-map.md|
|AI Workflow Prototype|Implemented and tested prototype, if completed|automation/|
|Project Documentation|Methods, limitations, and instructions for reproducing the work|README.md|

---

## 13. Author

**ALEX ESIVBEKPE**
**Business Data & AI Automation Analyst**

- 🔗 LinkedIn: www.linkedin.com/in/alex-esivbekpe
- 💼 GitHub: https://github.com/alexdanalyst/alexdanalyst
- 🌐 Portfolio: https://alexdanalyst.github.io

---



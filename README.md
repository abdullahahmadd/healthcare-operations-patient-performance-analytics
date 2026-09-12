# Healthcare Operations & Patient Performance Analytics

![GitHub Visitors](https://komarev.com/ghpvc/?username=abdullahahmadd&repo=healthcare-operations-patient-performance-analytics&label=Repository%20Views&color=0e75b6&style=flat)
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Excel](https://img.shields.io/badge/Excel-Data%20Preparation-217346?logo=microsoftexcel)
![Tableau](https://img.shields.io/badge/Tableau-Public-E97627?logo=tableau)

---

## Table of Contents

- [Overview](#overview)
- [Business Problem](#business-problem)
- [Objectives](#objectives)
- [Stakeholders](#stakeholders)
- [Dataset](#dataset)
- [Tools & Technologies](#tools--technologies)
- [Methodology](#methodology)
- [Data Model](#data-model)
- [Key Performance Indicators](#key-performance-indicators)
- [Dashboard Results](#dashboard-results)
- [Key Findings](#key-findings)
- [Business Recommendations](#business-recommendations)
- [Challenges & Solutions](#challenges--solutions)
- [Repository Structure](#repository-structure)
- [Conclusion](#conclusion)
- [Author](#author)

---

## Overview

This project simulates a Saudi healthcare network operating across multiple facilities, departments, physicians, services, diagnoses, and payers over the 2023-2025 period, transforming raw multi-domain healthcare data into measurable operational, financial, patient experience, quality, and provider-performance insight. The solution combines Python/Pandas for data preparation, Excel for structured analytical data storage, and Tableau Public for multi-fact relationship modeling, KPI development, and dashboarding - delivered as 6 management-focused dashboards.

---

## Business Problem

Healthcare organizations generate data across multiple operational processes - patient encounters, appointments, bed utilization, claims, surveys, pharmacy, laboratory, imaging, and physician activity. Analyzed independently, these datasets make it difficult for management to understand the relationship between patient demand and hospital capacity, revenue and treatment cost, waiting time and patient satisfaction, appointment cancellations and operational efficiency, readmissions and quality, physician productivity and service profitability, or payer collection and outstanding claims.

This project addresses these challenges by creating a centralized healthcare BI solution that connects multiple business processes through shared dimensions while preserving the correct grain of each fact table.

---

## Objectives

- Build a reproducible healthcare data-preparation workflow using Python and Pandas
- Convert raw data into validated analytical fact and dimension tables
- Preserve business-process grain and prevent measure duplication caused by inappropriate joins
- Implement a Tableau multi-fact relationship model using shared dimensions
- Develop standardized financial, operational, quality, patient, and provider KPIs, benchmarked against defined targets
- Deliver 6 portfolio-grade Tableau dashboards for management decision-making

---

## Stakeholders

| Stakeholder | Primary Decision Needs |
|---|---|
| Executive Management | Revenue, profitability, encounters, satisfaction, overall performance |
| Hospital Operations Managers | Capacity, bed utilization, appointments, cancellations, waiting time |
| Finance & Revenue Cycle Teams | Revenue, cost, profitability, claims, payer collection |
| Quality & Patient Experience Teams | Satisfaction, outcomes, readmissions, survey coverage |
| Medical Management | Physician productivity, service volume, treatment efficiency |
| Department Managers | Revenue, encounter activity, operational performance |
| Facility Managers | Facility utilization, demand, capacity and operational trends |

---

## Dataset

Synthetic Saudi healthcare network dataset covering January 2023 through December 2025, in SAR.

**Network coverage:** 30,000 patients, 75,000 encounters, 10 facilities, 15 departments, 60 physicians, 25 services, 30 diagnoses, 8 payers.

**Fact tables:**

| Fact Table | Grain | Records | Business Purpose |
|---|---|---:|---|
| `FACT_ENCOUNTER` | One encounter | 75,000 | Clinical, operational, financial performance |
| `APPOINTMENTS` | One appointment | 5,000 | Scheduling and cancellation analysis |
| `BED_UTILIZATION` | One facility-day | 10,960 | Capacity and bed utilization |
| `CLAIMS` | One claim | 8,000 | Claims and payer collection |
| `PATIENT_SURVEYS` | One survey | 6,000 | Patient experience |
| `PHARMACY` | One pharmacy transaction | 7,000 | Pharmacy activity |
| `LAB_TRANSACTIONS` | One lab transaction | 7,000 | Laboratory activity |
| `IMAGING` | One imaging transaction | 5,000 | Imaging activity |

**Dimension tables:** `DIM_PATIENT` (30,000), `DIM_DATE` (1,096), `DIM_FACILITY` (10), `DIM_DEPARTMENT` (15), `DIM_PHYSICIAN` (60), `DIM_SERVICE` (25), `DIM_DIAGNOSIS` (30), `DIM_PAYER` (8).

---

## Tools & Technologies

| Category | Tools |
|---|---|
| Data Preparation | Python, Pandas, Google Colab |
| Data Storage | Microsoft Excel |
| BI & Visualization | Tableau Public - calculated fields, KPI cards, target/reference lines, multi-fact relationship modeling |
| Documentation & Versioning | Microsoft Word, Markdown, GitHub |

---

## Methodology

**1. Original Dataset**
Started with an Excel healthcare dataset containing multiple business-process tables (patients, encounters, facilities, departments, physicians, services, diagnoses, payers, appointments, bed utilization, claims, surveys, pharmacy, laboratory, imaging).

**2. Data Exploration (Python/Pandas)**
Loaded and inspected the workbook in Google Colab - reviewing table structures, record counts, column names, data types, key fields, fact-table grain, date coverage, and entity relationships.

**3. Data Cleaning & Transformation (Python/Pandas)**
Standardized identifiers, dates, and categorical fields; prepared analytical dimensions and fact tables; created derived financial, operational, and quality measures; validated business logic and cross-table consistency.

**4. Analytical Data Model (Excel)**
Exported the transformed data into a structured workbook containing 8 dimension tables and 8 fact tables with standardized keys and validated record counts, ready for Tableau ingestion.

**5. Tableau Data Connection**
Connected the validated workbook to Tableau Public, avoiding a single flat-joined table since encounters, appointments, claims, surveys, and utilization records each represent distinct business processes.

**6. Multi-Fact Relationship Model (Tableau)**
Modeled `FACT_ENCOUNTER` against all 8 dimensions, and connected each supporting fact table to its relevant shared dimensions (see Data Model below), preventing measure multiplication from inappropriate physical joins.

**7. KPI & Calculated Field Development (Tableau)**
Built calculated fields for revenue, cost, gross profit, profit margin, encounter volume, waiting time, bed utilization, cancellations, satisfaction, readmissions, claims collection, physician productivity, and service efficiency.

**8. Dashboard Development (Tableau)**
Built 6 dashboards, each scoped to a distinct management decision domain (see Dashboard Results below).

**9. Validation & Quality Assurance**
Validated row counts, column counts, date coverage, key fields, and financial control totals (Revenue: SAR 110,077,066.91; Cost: SAR 66,470,103.04; Gross Profit: SAR 43,606,963.87) at both the Python export stage and the Tableau dashboard stage.

**10. Dashboard Export & Portfolio Packaging**
Finalized and exported all 6 dashboards as PDF and PNG, separated original/transformed datasets, preserved the data-preparation notebook, and produced detailed Word documentation for portfolio presentation.

---

## Data Model

The project uses a dimensional healthcare data model with multiple fact tables and shared dimensions rather than one flattened table.

**Main fact table - `FACT_ENCOUNTER`:** one record per healthcare encounter, including encounter/patient/date/facility/department/physician/service/diagnosis/payer IDs, encounter type, treatment cost, revenue, gross profit, wait time, service time, readmission indicator, and outcome.

**Shared dimensions:** Date, Patient, Facility, Department, Physician, Service, Diagnosis, Payer.

**Supporting fact relationships:**

| Fact Table | Shared Dimensions |
|---|---|
| `APPOINTMENTS` | Date, Patient, Facility, Department, Physician |
| `BED_UTILIZATION` | Date, Facility |
| `CLAIMS` | Date, Patient, Payer |
| `PATIENT_SURVEYS` | Date, Patient |
| `PHARMACY` | Date, Patient |
| `LAB_TRANSACTIONS` | Date, Patient |
| `IMAGING` | Date, Patient |

This architecture preserves each fact table's native grain and prevents inaccurate aggregation from unrelated business processes being physically joined together.

---

## Key Performance Indicators

| KPI | Actual Result | Target / Benchmark |
|---|---:|---:|
| Service Revenue | SAR 110.1M | - |
| Treatment Cost | SAR 66.5M | - |
| Gross Profit | SAR 43.6M | - |
| Gross Profit Margin | 39.6% | >= 35% |
| Total Encounters | 75,000 | - |
| Average Wait Time | 21.2 min | <= 20 min |
| Patient Satisfaction | 4.52 / 5 | >= 4.5 |
| Bed Utilization | 77.8% | 75-85% |
| Readmission Rate | 6.51% | <= 6% |
| Appointment Cancellation Rate | 6.0% | <= 5% |
| Avg Revenue / Encounter | SAR 1,468 | - |
| Avg Cost / Encounter | SAR 886 | - |
| Avg Gross Profit / Encounter | SAR 581 | - |
| Survey Coverage Rate | 20.0% | - |
| Revenue / Treatment Minute | SAR 12.15 | - |
| Outstanding Claim Value | ~SAR 1.2M | 90% collection benchmark |
| Avg Encounters / Physician | 1,250 | - |
| Avg Revenue / Physician | ~SAR 1.8M | - |

---

## Dashboard Results

All dashboard screenshots in [`05_Dashboards/`](./05_Dashboards).

### 1. Healthcare Executive Performance Overview

![Healthcare Executive Performance Overview](05_Dashboards/01_Healthcare_Executive_Performance_Overview.pdf)

Consolidated view of financial performance, encounter volume, patient satisfaction, and payer revenue for executive management. **Results:** SAR 110.1M service revenue, SAR 43.6M gross profit, 39.6% margin, 75,000 encounters, 4.52/5 satisfaction. **Use:** monitor enterprise performance, compare revenue vs. cost, review profitability against the 35% benchmark.

### 2. Patient & Utilization Analytics

![Patient & Utilization Analytics](05_Dashboards/02_Patient_Utilization_Analytics.pdf)

Analyzes patient demand distribution, encounter-mix, and utilization patterns across departments and facilities. **Use:** align patient demand with service capacity, staff allocation, and operational planning.

### 3. Hospital Operations & Capacity

![Hospital Operations & Capacity](05_Dashboards/03_Hospital_Operations_Capacity.pdf)

Measures facility capacity, bed utilization, appointment activity, cancellations, and waiting time. **Results:** 3,190 total bed capacity, 77.8% bed utilization (within 75-85% target), 5,000 appointments, 6.0% cancellation rate (above 5% target), 21.2 min average wait (above 20 min target). **Recommendation:** reduce wait time to <=20 min and cancellations to <=5%.

### 4. Financial & Revenue Analytics

![Financial & Revenue Analytics](05_Dashboards/04_Financial_Revenue_Analytics.pdf)

Evaluates revenue generation, treatment cost, profitability, service economics, and payer collection. **Results:** SAR 66.5M total treatment cost, SAR 1,468 avg revenue/encounter, SAR 886 avg cost/encounter, SAR 581 avg gross profit/encounter, ~SAR 1.2M outstanding claim value against a 90% collection benchmark. **Recommendation:** maintain gross margin above 35% while prioritizing payers/services needing collection or cost-efficiency improvement.

### 5. Patient Experience & Quality

![Patient Experience & Quality](05_Dashboards/05_Patient_Experience_Quality.pdf)

Evaluates satisfaction, patient outcomes, survey coverage, and readmission performance. **Results:** 6,000 survey responses, 4.52/5 satisfaction (above 4.5 target), 60.0% satisfaction-within-target, 75.5% positive outcome rate, 20.0% survey coverage, 6.51% overall readmission (above 6% target). **Encounter-type finding:** inpatient readmission runs ~9.8% vs. 5.7% outpatient and 5.4% emergency. **Recommendation:** prioritize inpatient readmission reduction and expand survey participation.

### 6. Physician & Service Performance

![Physician & Service Performance](05_Dashboards/06_Physician_Service_Performance.pdf)

Evaluates provider productivity and service-level financial efficiency. **Results:** 60 physicians, 1,250 avg encounters/physician, ~SAR 1.8M avg revenue/physician, 142.0 min avg service time, SAR 12.15 revenue/treatment minute. **Use:** identify workload imbalances, high-performing services, and revenue-efficiency opportunities.

---

## Key Findings

- **Profitability is strong and above benchmark:** SAR 110.1M revenue against SAR 66.5M cost produces a 39.6% gross margin, exceeding the 35% reference target - but this margin needs department/service-level monitoring to catch cost-growth risk before it erodes the buffer.
- **Two operational KPIs are missing target simultaneously (wait time and cancellations), while bed utilization is on target** - this points to a scheduling/patient-flow problem specifically, not a general capacity shortage, since bed utilization being within range rules out the "not enough capacity" explanation.
- **Overall readmission (6.51%) is only marginally above target, but inpatient readmission (9.8%) is nearly double outpatient and emergency rates** - aggregating readmission as one number would have hidden a problem that is actually concentrated almost entirely in one encounter type.
- **Patient satisfaction (4.52/5) clears its target, but only 20% of patients are surveyed** - a high average score built on a fifth of the patient population is a weaker signal than the raw number suggests, and expanding coverage should be treated as a data-reliability fix, not just a nice-to-have.
- **Claims collection risk (~SAR 1.2M outstanding) sits alongside strong headline profitability** - profitability figures based on billed revenue can overstate realized cash position if outstanding claims aren't tracked and closed against the 90% collection benchmark.

---

## Business Recommendations

1. **Reduce average wait time from 21.2 to <=20 minutes** by reviewing patient flow from registration to consultation, balancing physician workload, and monitoring wait time by facility and encounter type.
2. **Reduce appointment cancellations from 6.0% to <=5%** through confirmation reminders, SMS/app notifications, and tracking cancellation reasons by department.
3. **Prioritize inpatient readmission reduction** given the 9.8% rate is nearly double outpatient/emergency - strengthen discharge planning, follow-up calls, and high-risk patient identification specifically for inpatient care.
4. **Expand patient survey coverage beyond 20%** using digital distribution, post-visit reminders, and QR-code access, to make satisfaction and outcome KPIs representative rather than a partial sample.
5. **Strengthen claims collection** by prioritizing payers with weaker performance, older outstanding claims, and documentation-related rejections, monitored against the 90% collection benchmark.
6. **Maintain bed utilization within the 75-85% range** while monitoring high-demand periods to avoid both underutilization and overcrowding.
7. **Use physician and service-level performance data for workforce planning** - encounters/physician, revenue/physician, and revenue/treatment-minute together identify workload imbalances and high-efficiency services worth expanding.
8. **Track profit margin at department and service granularity**, not just network-wide, to catch localized cost growth before it affects the overall 39.6% margin.

---

## Challenges & Solutions

| Challenge | Solution |
|---|---|
| Multiple fact tables with different business grains (encounters, appointments, claims, surveys, facility-day utilization, pharmacy, lab, imaging) risked record multiplication if physically joined | Implemented a Tableau multi-fact relationship model using shared dimensions while preserving each fact table's native grain |
| Preventing measure duplication (revenue, cost, encounter/appointment/claim counts) | Used Tableau relationships and distinct-count calculations instead of flattening all processes into one physical table |
| Cross-domain KPIs (survey coverage, claims collection, appointment performance) require fields from different processes | Used shared dimensions and fact-specific calculations while keeping each measure tied to its correct business grain |
| Raw healthcare records don't automatically produce management-ready insight | Converted raw measures into business KPIs - profit margin, revenue/encounter, bed utilization, cancellation rate, readmission rate, revenue/treatment minute |
| Risk of repetitive, overlapping dashboards given the dataset's breadth | Assigned each of the 6 dashboards a distinct decision domain (executive, patient/utilization, operations, financial, experience/quality, physician/service) so no two dashboards answer the same question |

---

## Repository Structure

```
healthcare-operations-patient-performance-analytics/
├── 01_Original_Dataset/
│   └── Healthcare_Operations_Patient_Performance_Analytics.xlsx
├── 02_Transformed_Dataset/
│   └── Healthcare_Operations_Patient_Performance_Analytics_Final.xlsx
├── 03_Notebook/
│   └── Healthcare_Operations_Patient_Performance_Analytics_Data_Preparation.ipynb
├── 04_Tableau/
│   └── Healthcare_Operations_Patient_Performance_Analytics.twb
├── 05_Dashboards/
│   ├── 01_Healthcare_Executive_Performance_Overview.pdf / .png
│   ├── 02_Patient_Utilization_Analytics.pdf / .png
│   ├── 03_Hospital_Operations_Capacity.pdf / .png
│   ├── 04_Financial_Revenue_Analytics.pdf / .png
│   ├── 05_Patient_Experience_Quality.pdf / .png
│   └── 06_Physician_Service_Performance.pdf / .png
└── 06_Documentation/
    └── Healthcare_Operations_Patient_Performance_Analytics_Documentation.docx
```

---

## Conclusion

Healthcare Operations & Patient Performance Analytics demonstrates a complete BI workflow from raw healthcare data to decision-ready management insight - combining Python/Pandas data preparation, structured Excel analytical modeling, Tableau multi-fact relationships, KPI development, interactive dashboards, data validation, and business recommendations across 75,000 encounters, 30,000 patients, 10 facilities, and 8 payers over 2023-2025. The analysis identifies concrete opportunities to reduce wait time and cancellations, lower inpatient readmissions, strengthen claims collection, increase survey coverage, and improve physician/service productivity, while protecting a profit margin that currently sits above benchmark.

---


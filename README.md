# Healthcare Operations & Patient Performance Analytics

![Visitors](https://komarev.com/ghpvc/?username=abdullahahmadd&repo=healthcare-operations-patient-performance-analytics&color=blue&style=flat-square&label=Repository+Views)
![Python](https://img.shields.io/badge/Python-Data%20Preparation-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Transformation-150458?logo=pandas)
![Tableau](https://img.shields.io/badge/Tableau-Public-E97627?logo=tableau)
![Excel](https://img.shields.io/badge/Excel-Data%20Modeling-217346?logo=microsoftexcel)
![Healthcare Analytics](https://img.shields.io/badge/Domain-Healthcare%20Analytics-2E7D32)

---

## Table of Contents

- [Overview](#overview)
- [Business Problem](#business-problem)
- [Project Objectives](#project-objectives)
- [Stakeholders](#stakeholders)
- [Dataset Description](#dataset-description)
- [Tools & Technologies Used](#tools--technologies-used)
- [Skills Demonstrated](#skills-demonstrated)
- [Key Metrics / KPIs](#key-metrics--kpis)
- [Project Workflow](#project-workflow)
- [Results](#results)
  - [1. Healthcare Executive Performance Overview](#1-healthcare-executive-performance-overview)
  - [2. Patient & Utilization Analytics](#2-patient--utilization-analytics)
  - [3. Hospital Operations & Capacity](#3-hospital-operations--capacity)
  - [4. Financial & Revenue Analytics](#4-financial--revenue-analytics)
  - [5. Patient Experience & Quality](#5-patient-experience--quality)
  - [6. Physician & Service Performance](#6-physician--service-performance)
- [Key Insights & Business Recommendations](#key-insights--business-recommendations)
- [Challenges & Solutions](#challenges--solutions)
- [Project Learnings](#project-learnings)
- [Repository Structure](#repository-structure)
- [Project Files & Deliverables](#project-files--deliverables)
- [Conclusion](#conclusion)

---

## Overview

**Healthcare Operations & Patient Performance Analytics** is an end-to-end Business Intelligence project designed to transform multi-domain healthcare data into actionable operational, financial, patient experience, quality, and provider-performance insights.

The project simulates a **Saudi healthcare network** operating across multiple facilities, departments, physicians, services, diagnoses, and payers over the **2023–2025** period.

The solution combines **Python/Pandas for data preparation**, **Excel for structured analytical data storage**, and **Tableau Public for multi-fact relationship modeling, KPI development, interactive analysis, and dashboarding**.

The final BI solution contains **6 management-focused dashboards** covering:

- Executive performance
- Patient and utilization analytics
- Hospital operations and capacity
- Financial and revenue performance
- Patient experience and quality
- Physician and service performance

The project is designed around measurable business outcomes, with KPI benchmarks for profitability, waiting time, patient satisfaction, bed utilization, readmissions, appointment cancellations, and claims collection.

---

## Business Problem

Healthcare organizations generate data across multiple operational processes, including patient encounters, appointments, bed utilization, claims, surveys, pharmacy, laboratory, imaging, and physician activity.

When these datasets are analyzed independently, management may struggle to answer critical questions such as:

- Are revenue and profitability meeting expectations?
- Which facilities and departments generate the highest activity?
- Is hospital capacity being utilized efficiently?
- Where are appointment cancellations and waiting times creating operational inefficiencies?
- Which payers require stronger claims-collection management?
- Is patient satisfaction meeting the required service-quality standard?
- Which encounter types have elevated readmission rates?
- Which physicians and services generate the strongest financial and operational performance?

This project addresses these challenges by creating a **centralized healthcare BI solution** that connects multiple business processes through shared dimensions while preserving the correct grain of each fact table.

---

## Project Objectives

The project was developed to:

1. Build a reproducible healthcare data-preparation workflow using Python and Pandas.
2. Convert the original dataset into validated analytical fact and dimension tables.
3. Preserve business-process grain and prevent measure duplication caused by inappropriate joins.
4. Implement a Tableau **multi-fact relationship model** using shared dimensions.
5. Develop standardized financial, operational, quality, patient, and provider KPIs.
6. Compare actual performance against defined business targets.
7. Identify measurable operational and financial improvement opportunities.
8. Deliver six portfolio-grade Tableau dashboards for management decision-making.
9. Produce a structured project package suitable for professional BI portfolio presentation.

---

## Stakeholders

The dashboards are designed to support different healthcare decision-makers:

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

## Dataset Description

The project uses a **synthetic Saudi healthcare network dataset** covering the period from **January 2023 through December 2025**.

### Network Coverage

| Dimension | Records |
|---|---:|
| Patients | 30,000 |
| Encounters | 75,000 |
| Facilities | 10 |
| Departments | 15 |
| Physicians | 60 |
| Services | 25 |
| Diagnoses | 30 |
| Payers | 8 |
| Analytical Period | 2023–2025 |
| Currency | SAR |

### Fact Tables

| Fact Table | Grain | Records | Business Purpose |
|---|---|---:|---|
| `FACT_ENCOUNTER` | One encounter | 75,000 | Clinical, operational and financial performance |
| `APPOINTMENTS` | One appointment | 5,000 | Scheduling and cancellation analysis |
| `BED_UTILIZATION` | One facility-day | 10,960 | Capacity and bed utilization |
| `CLAIMS` | One claim | 8,000 | Claims and payer collection |
| `PATIENT_SURVEYS` | One survey | 6,000 | Patient experience |
| `PHARMACY` | One pharmacy transaction | 7,000 | Pharmacy activity |
| `LAB_TRANSACTIONS` | One laboratory transaction | 7,000 | Laboratory activity |
| `IMAGING` | One imaging transaction | 5,000 | Imaging activity |

### Dimension Tables

| Dimension | Records | Purpose |
|---|---:|---|
| `DIM_PATIENT` | 30,000 | Patient attributes |
| `DIM_DATE` | 1,096 | Date and time analysis |
| `DIM_FACILITY` | 10 | Facility attributes |
| `DIM_DEPARTMENT` | 15 | Department attributes |
| `DIM_PHYSICIAN` | 60 | Physician attributes |
| `DIM_SERVICE` | 25 | Service attributes |
| `DIM_DIAGNOSIS` | 30 | Diagnosis attributes |
| `DIM_PAYER` | 8 | Payer attributes |

---

## Tools & Technologies Used

| Tool / Technology | Application |
|---|---|
| **Python** | Data preparation and transformation |
| **Pandas** | Data manipulation, cleaning and validation |
| **Google Colab** | Reproducible notebook environment |
| **Microsoft Excel** | Structured analytical dataset storage |
| **Tableau Public** | BI modeling, calculations, visualization and dashboards |
| **GitHub** | Project versioning and portfolio presentation |
| **Markdown** | Technical project documentation |

---

## Skills Demonstrated

### Data Preparation
- Data inspection
- Data cleaning
- Data standardization
- Data transformation
- Feature/measure derivation
- Data validation
- Control-total validation

### Data Modeling
- Fact and dimension design
- Business-process grain identification
- Primary/foreign key relationships
- Multi-fact relationship modeling
- Shared dimensions
- Prevention of measure multiplication
- Analytical model design

### Tableau & BI
- Tableau relationship modeling
- Multi-fact architecture
- Calculated fields
- KPI development
- Target/reference lines
- Top-N analysis
- Trend analysis
- Comparative analysis
- Dashboard layout and formatting
- Executive dashboard design

### Business Analytics
- Financial performance analysis
- Operational efficiency analysis
- Capacity analysis
- Patient experience analysis
- Quality analysis
- Provider performance analysis
- Revenue-cycle analysis
- Business recommendations

---

## Key Metrics / KPIs

The project uses measurable KPIs aligned with healthcare operational and financial priorities.

| KPI | Actual Result | Target / Benchmark |
|---|---:|---:|
| Service Revenue | **SAR 110.1M** | — |
| Treatment Cost | **SAR 66.5M** | — |
| Gross Profit | **SAR 43.6M** | — |
| Gross Profit Margin | **39.6%** | ≥ 35% |
| Total Encounters | **75,000** | — |
| Average Wait Time | **21.2 min** | ≤ 20 min |
| Patient Satisfaction | **4.52 / 5** | ≥ 4.5 |
| Bed Utilization | **77.8%** | 75–85% |
| Readmission Rate | **6.51%** | ≤ 6% |
| Appointment Cancellation Rate | **6.0%** | ≤ 5% |
| Avg Revenue / Encounter | **SAR 1,468** | — |
| Avg Cost / Encounter | **SAR 886** | — |
| Avg Gross Profit / Encounter | **SAR 581** | — |
| Survey Coverage Rate | **20.0%** | — |
| Revenue / Treatment Minute | **SAR 12.15** | — |

---

# Project Workflow

The project follows a complete BI storytelling workflow from raw data to management insights.

### 1. Original Dataset

The project began with the original Excel healthcare dataset containing multiple business-process tables.

The raw dataset provided the foundation for:

- Patient records
- Healthcare encounters
- Facilities
- Departments
- Physicians
- Services
- Diagnoses
- Payers
- Appointments
- Bed utilization
- Claims
- Patient surveys
- Pharmacy
- Laboratory
- Imaging

---

### 2. Data Exploration — Python / Pandas

The original dataset was loaded and inspected using **Python and Pandas in Google Colab**.

The preparation stage focused on:

- Reviewing table structures
- Checking record counts
- Reviewing column names
- Inspecting data types
- Identifying key fields
- Understanding fact-table grain
- Reviewing date coverage
- Identifying relationships between entities

This established the analytical structure before transformation.

---

### 3. Data Cleaning & Transformation — Python / Pandas

The datasets were transformed into analysis-ready tables.

Key activities included:

- Standardizing identifiers
- Standardizing dates and categorical fields
- Preparing analytical dimensions
- Preparing business-process fact tables
- Creating derived analytical measures
- Preparing financial calculations
- Preparing operational measures
- Preparing quality indicators
- Validating analytical fields

The objective was to create a reliable dataset that could be consumed by Tableau without requiring extensive manual preprocessing.

---

### 4. Analytical Data Model — Excel

The transformed datasets were exported into a structured Excel workbook.

The final analytical workbook contains:

- **8 dimension tables**
- **8 fact tables**
- Standardized keys
- Consistent analytical fields
- Validated record counts
- Business-ready measures

The final export was validated before Tableau ingestion.

---

### 5. Tableau Data Connection

The validated analytical workbook was connected to **Tableau Public**.

Instead of physically joining all datasets into one flat table, the project used Tableau's relationship architecture to preserve the native grain of each business process.

---

### 6. Multi-Fact Relationship Model — Tableau

A **multi-fact relationship model** was implemented.

`FACT_ENCOUNTER` was modeled with:

- `DIM_DATE`
- `DIM_PATIENT`
- `DIM_FACILITY`
- `DIM_DEPARTMENT`
- `DIM_PHYSICIAN`
- `DIM_SERVICE`
- `DIM_DIAGNOSIS`
- `DIM_PAYER`

Supporting facts were connected through appropriate shared dimensions.

This architecture was selected to prevent incorrect aggregation and **measure multiplication** that could occur if unrelated facts were physically joined together.

---

### 7. KPI & Calculated Field Development — Tableau

Business KPIs were developed to measure:

- Revenue
- Cost
- Gross profit
- Profit margin
- Encounter volume
- Waiting time
- Bed utilization
- Appointment cancellations
- Patient satisfaction
- Readmissions
- Claims collection
- Physician productivity
- Service efficiency

Representative calculations included:

```text
Gross Profit
= Service Revenue − Treatment Cost

Profit Margin
= Gross Profit ÷ Service Revenue

Average Revenue / Encounter
= Service Revenue ÷ Distinct Encounters

Average Cost / Encounter
= Treatment Cost ÷ Distinct Encounters

Revenue / Treatment Minute
= Service Revenue ÷ Treatment Time Minutes

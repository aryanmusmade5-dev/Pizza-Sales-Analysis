# 🍕 01 — Business Analysis: Pizza Sales Analysis

| Field | Value |
|---|---|
| **Project** | Pizza Sales Analysis — end-to-end portfolio project (SQL, Python, Excel, Power BI, Tableau) |
| **Stage** | 01 — Business Analysis (precedes all SQL, Python, Excel, Power BI, and Tableau work) |
| **Analysis type** | Descriptive sales analysis |
| **Source data** | Supplied CSV/XLSX file and project brief (`pizza_sales.csv`; see [Reported dataset profile](#-4-reported-dataset-profile)) |
| **Audience** | Business stakeholders, analysts, recruiters, and project reviewers. |
| **Folder status** | Definitions, requirements, and questions are written. **No analysis results are recorded in this folder by design.** |

---
##  🎯 Business Objective

Analyze pizza sales data to understand overall sales performance, time-based sales patterns, product performance, and order behavior, enabling better decisions around marketing, menu optimization, staffing, and inventory planning.


## 🎯 1. Purpose of This Folder

This folder explains the business problem **before** any SQL, Python, Excel, Power BI, or Tableau work begins. It records what the business needs to understand, which measures matter, and what questions the analysis must answer.

It is a descriptive sales-analysis project: its purpose is to turn transaction data into trustworthy performance measures and useful business decisions — not merely to create attractive dashboards.

## 📁 2. Files in This Folder

| File | Contents | Read it to learn… |
|---|---|---|
| [`Business-Problem.md`](Business-Problem.md) | Business context, problem statement, objectives, stakeholders, scope, analysis principles, deliverables, definition of success | **Why** the project exists |
| [`Business-Requirements.md`](Business-Requirements.md) | Stakeholder and functional requirements, data foundation, assumptions, constraints, decisions, acceptance criteria, traceability, open questions | **What** the analysis must deliver |
| [`KPIs.md`](KPIs.md) | KPI definitions, formulas, units, cautions, naming conventions, quality checklist | **How** each measure is calculated |
| [`Business-Questions.md`](Business-Questions.md) | The 29 analysis questions, suggested outputs, answer template, question-to-analysis map | **What to answer** and where the answer lives |

## 🧭 3. How to Use This Folder

1. Read [`Business-Problem.md`](Business-Problem.md) to understand *why* the project exists.
2. Read [`Business-Requirements.md`](Business-Requirements.md) to understand *what* the analysis must deliver.
3. Confirm KPI definitions in [`KPIs.md`](KPIs.md) **before** writing queries or building charts.
4. Use [`Business-Questions.md`](Business-Questions.md) as the checklist for SQL analysis and dashboard design.
5. Check the open questions in [`Business-Requirements.md`](Business-Requirements.md#-10-open-questions) before relying on any unconfirmed assumption.
6. Update these documents if the source data or agreed business scope changes (see [Maintenance](#-7-maintenance)).

## 📊 4. Reported Dataset Profile

Reported by the project owner; **verify during data validation** before relying on it:

- File: `pizza_sales.csv`
- Approximately 48,620 rows and 12 columns
- Data from 2015

Column names, data types, and row grain are **not yet confirmed** in this folder (see open questions OQ-1 and OQ-2 in [`Business-Requirements.md`](Business-Requirements.md#-10-open-questions)).

### 🚨 Data note (critical)
The exact dataset schema and business definitions **must be confirmed** against the supplied CSV/XLSX file and project brief. Do not invent missing values, costs, profit, customer demographics, or operational details. Where the dataset does not contain a field, record it as **unavailable** rather than estimating it without a documented method.

## 📌 5. Order of Precedence

When sources disagree, apply this order (highest first):

1. Facts confirmed by inspecting the actual dataset.
2. The project brief and any documented business definition.
3. The definitions in this folder.

If a confirmed fact or the project brief requires a different definition, **update this folder first** (starting with [`KPIs.md`](KPIs.md) for KPI changes), then use the new definition everywhere else.

## 🤖 6. Analysis & Documentation Standards

These rules are mandatory when generating queries, charts, summaries, or recommendations for this project.

1. **Do not invent data.** Never fabricate or estimate missing values, costs, profit, customer demographics, or operational details. If a field is absent, record it as **unavailable** unless an estimation method is documented and approved.
2. **Do not pre-fill results.** These documents define questions, not answers. Record results only after the analysis has run and been validated.
3. **Use KPI definitions exactly as written in [`KPIs.md`](KPIs.md)**, including the canonical KPI names.
4. **Revenue is not profit.** Never describe revenue as profit or revenue ranking as profitability.
5. **Stay descriptive.** Do not make causal claims ("sales fell *because*…") from descriptive sales data alone.
6. **Separate fact, interpretation, and recommendation.** Label each clearly.
7. **Resolve ambiguity openly.** If the dataset grain, revenue field, or a definition is unclear, state the assumption explicitly and add it to the open questions rather than silently choosing an interpretation.
8. **Keep scope and filters consistent.** Use the same date range and filters when comparing measures, and the same scope for numerators and denominators.

## 🔧 7. Maintenance

- Update the relevant file whenever the source data or agreed business scope changes, and *before* changing definitions elsewhere in the project.
- Record any KPI definition change in [`KPIs.md`](KPIs.md) and keep the naming conventions in sync.
- Update assumption statuses and open questions in [`Business-Requirements.md`](Business-Requirements.md) and deliverable statuses in [`Business-Problem.md`](Business-Problem.md) as they are resolved.
- Keep results out of this folder; record them in the analysis outputs (SQL, notebooks, dashboards, and `08_Insights_and_Recommendations/`).

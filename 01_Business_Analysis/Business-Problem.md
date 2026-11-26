# 🍕 Business Problem — Pizza Sales Analysis

> Part of [`01_Business_Analysis`](README.md). Related: [Requirements](Business-Requirements.md) · [KPIs](KPIs.md) · [Questions](Business-Questions.md)

## 🔭 1. Project Overview

A pizza business generates order-level sales data, but raw transaction records alone do not explain how the business is performing. Management needs a clear view of revenue, order volume, **order and product purchasing patterns**, product performance, and changes in demand over time.

This project analyzes the available pizza sales dataset and translates the findings into practical information that can support sales planning, menu decisions, marketing activities, staffing, and inventory planning.

## 🌍 2. Business Context

A pizza store typically sells multiple pizza types, categories, and sizes across different days and times. Sales can vary by product, order volume, day of week, and time of day. Without a consistent analysis, managers may find it difficult to answer questions such as:

- Which products and categories contribute most to sales?
- When is demand highest or lowest?
- Are sales driven by a small number of popular products?
- Which products may need promotion, menu review, or further investigation?
- How can demand patterns inform staffing and stock planning?

> These are questions to investigate, **not conclusions to assume in advance.**

## 🎯 3. Problem Statement

> **The business needs a reliable, understandable analysis of pizza sales data to identify sales performance patterns and product-level opportunities, so management can make better-informed decisions about sales, marketing, menu optimization, staffing, and inventory.**

**Business objective (requirements view):** provide a consistent view of sales performance and product/time patterns from the available pizza sales dataset so stakeholders can make better-informed decisions about sales, promotions, menu planning, staffing, and inventory.

### Business Decisions Supported

| Business Decision         | Analysis                                      |
| ------------------------- | --------------------------------------------- |
| Improve sales performance  | Revenue, orders, pizzas sold                  |
| Plan staffing              | Orders by weekday/hour                        |
| Optimize menu              | Product/category/size performance             |
| Plan inventory              | Pizza quantity by product/time                |
| Improve promotions          | High/low performing products and time periods |

## 🏁 4. Objectives

| ID | Objective | Detail |
|---|---|---|
| OBJ-1 | **Measure overall performance** | Establish total revenue, total orders, pizzas sold, and average order value using consistent definitions. |
| OBJ-2 | **Understand time patterns** | Analyze sales by date, day of week, and time of day where the source fields support it. |
| OBJ-3 | **Evaluate product performance** | Compare pizza types, categories, and sizes using revenue, quantity, and order-related measures. |
| OBJ-4 | **Identify contribution and concentration** | Determine which products or groups contribute most and least to the selected measures. |
| OBJ-5 | **Create actionable findings** | Explain what the results mean for the business and propose recommendations proportionate to the evidence. |
| OBJ-6 | **Communicate clearly** | Prepare reproducible analysis and dashboards that stakeholders can understand and use. |

## 👥 5. Stakeholders

These are **proposed stakeholder groups used to frame the analysis**; they are not claims about the actual organization.

| Stakeholder | Likely need | How this project can help |
|---|---|---|
| Store manager | Understand overall performance and demand patterns | KPI summary and time-based analysis |
| Owner / leadership | See sales contribution and areas for improvement | Executive summary and prioritized insights |
| Marketing team | Identify products or periods worth testing in campaigns | Product and time-pattern findings |
| Menu / product manager | Understand relative product performance | Category, size, and pizza-level comparisons |
| Operations / inventory team | Plan around observed demand | Day/time and product-quantity patterns, subject to data coverage |

## 📐 6. Scope

### ✅ 6.1 In scope

- Inspecting and validating the provided pizza sales data.
- Defining business KPIs and calculation rules.
- Measuring revenue, orders, pizzas sold, and average order value.
- Analyzing sales by date, weekday, and time where possible.
- Comparing product names/types, categories, and sizes where available.
- Identifying highest- and lowest-performing products using clearly stated measures.
- Presenting findings through SQL, Python, Excel, Power BI, and/or Tableau deliverables in the wider project.
- Writing evidence-based insights and recommendations.

### 🚫 6.2 Out of scope (unless additional data is supplied)

| Out-of-scope item | Condition / reason |
|---|---|
| Profit margin or profitability analysis | Costs are unavailable |
| Customer segmentation, lifetime value, repeat-customer analysis | Customer identifiers are unavailable |
| Marketing campaign attribution or return on ad spend | No campaign or cost data |
| Forecasting future demand | Only if a forecasting method and sufficient historical data are explicitly added |
| Causal claims about why sales changed | Data is descriptive only |
| Claims about waste, stockouts, labor productivity, or service quality | No relevant operational fields |

## 🧭 7. Analysis Principles

- Start with business questions, not charts.
- Use the same date range and filters when comparing measures.
- Label monetary values and units clearly.
- Separate observed facts from interpretation and recommendations.
- Do not describe revenue as profit.
- Do not claim a product is "bad" solely because it has low sales; consider its role, price, costs, availability, and business strategy **if those data exist**.
- Record assumptions and data limitations explicitly.

## 📦 8. Expected Deliverables

The final project must **distinguish completed deliverables from planned or optional ones.** Update the status column as work progresses.

| Deliverable | Status |
|---|---|
| Documented business problem and requirements | ☐ |
| Data dictionary and validation record | ☐ |
| Reproducible SQL analysis | ☐ |
| Python exploratory analysis and data-quality checks (if used) | ☐ |
| Excel analysis/dashboard | ☐ |
| Power BI dashboard | ☐ |
| Tableau dashboard | ☐ |
| Final report: findings, limitations, and recommendations | ☐ |

## 🏆 9. Definition of Success

The project is successful when:

- KPI definitions are documented and consistently applied.
- Source data quality issues are checked and disclosed.
- Results can be reproduced from the source data.
- Dashboard totals reconcile with validated analysis.
- Each major business question has a result **or a clear explanation of why it cannot be answered**.
- Recommendations are linked to evidence and include appropriate caveats.
- A reader can understand the business problem and the project outcome without inspecting every query.

## 📝 10. Project Summary

This is a descriptive sales-analysis project. Its purpose is to turn transaction data into trustworthy performance measures and useful business decisions — not merely to create attractive dashboards.
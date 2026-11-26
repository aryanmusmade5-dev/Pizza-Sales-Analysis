# 🍕 Business Requirements — Pizza Sales Analysis

> Part of [`01_Business_Analysis`](README.md). Related: [Problem](Business-Problem.md) · [KPIs](KPIs.md) · [Questions](Business-Questions.md)

---

## 🎯 1. Purpose

This document defines the information the pizza sales analysis should provide, the rules it should follow, and how the deliverables will be evaluated. The business objective is stated in [Business-Problem.md](Business-Problem.md#-3-problem-statement).

---

## 👥 2. Stakeholder (Business) Requirements

| ID | Requirement | Expected output |
|---|---|---|
| BR-01 | Understand overall sales performance | KPI summary |
| BR-02 | Understand order volume and pizza quantity | Orders and quantity measures |
| BR-03 | Understand average order value | Clearly defined AOV measure |
| BR-04 | Compare performance over time | Daily, weekday, and hourly trends where supported |
| BR-05 | Compare product groups | Category and size analysis |
| BR-06 | Identify top and bottom products | Ranked product views with the measure stated |
| BR-07 | Support decisions with evidence | Findings and recommendations |
| BR-08 | Trust the results | Data validation and reconciliation |
| BR-09 | Navigate the results efficiently | Clear labels, filters, and readable dashboards |
| BR-10 | Reproduce the analysis | Saved SQL/scripts/workbooks and documented methods |

---

## 🔧 3. Functional Requirements

### Data and validation

- **FR-01:** Load the supplied source data without silently changing its meaning.
- **FR-02:** Inspect column names, data types, date formats, missing values, duplicates, and invalid or inconsistent records.
- **FR-03:** Validate numeric fields such as quantity and unit price for reasonable values.
- **FR-04:** Document all cleaning or exclusion rules and their impact.
- **FR-05:** Confirm the grain of the dataset (see [§5.1](#51-dataset-grain)) before calculating distinct orders or quantities.

### KPI analysis

- **FR-06:** Calculate total revenue from the agreed revenue field or documented formula.
- **FR-07:** Calculate total pizzas sold from the quantity field.
- **FR-08:** Calculate total orders using a distinct order identifier, if available.
- **FR-09:** Calculate average order value as total revenue ÷ distinct orders, if those fields are valid.
- **FR-10:** Reconcile headline KPIs across SQL and dashboard tools.

### Time analysis

- **FR-11:** Analyze revenue and/or order volume over time.
- **FR-12:** Compare weekdays and time-of-day periods when date/time fields are available.
- **FR-13:** Use a consistent calendar and time grouping across visuals.

### Product analysis

- **FR-14:** Compare sales by pizza category.
- **FR-15:** Compare sales by pizza size.
- **FR-16:** Rank pizza types/products by revenue and quantity.
- **FR-17:** Identify low-performing products **separately for each chosen metric**; do not imply that low revenue automatically means low profitability.

### Reporting

- **FR-18:** Provide readable KPI definitions, chart titles, units, and filter context.
- **FR-19:** Summarize key findings with supporting figures from the completed analysis.
- **FR-20:** Provide recommendations linked to findings, identifying any assumptions or tests required.

---

## 🧱 4. Non-Functional Requirements

| Quality | Requirement |
|---|---|
| **Accuracy** | Totals reconcile to the validated source data. |
| **Consistency** | KPI formulas and filters match across tools. |
| **Traceability** | Analysis steps are documented and reproducible. |
| **Clarity** | Visuals use meaningful titles, labels, and units. |
| **Maintainability** | Filenames and folders make the project easy to navigate. |
| **Honesty** | Unavailable data and unanswered questions are disclosed. |

---

## 💾 5. Data Foundation

### 5.1 Dataset grain

The grain (what one row represents — for example, an order line or another transaction unit) **must be confirmed before** calculating distinct orders or quantities (FR-05). An order can contain multiple pizza line items, so counting rows can overstate order count. Reported dataset profile and the critical data note are in the [README](README.md#-4-reported-dataset-profile).

### 5.2 KPI quick reference

Proposed starting definitions, to be confirmed against the dataset and project brief. **Full definitions, cautions, and naming conventions live in [`KPIs.md`](KPIs.md), which is the source of truth.**

| KPI | Proposed definition | Validation note |
|---|---|---|
| Total Revenue | Sum of the line-level sales/revenue amount, or quantity × unit price if no revenue field exists | Check whether discounts, tax, or refunds are included |
| Total Pizzas Sold | Sum of quantity | Confirm each row's meaning |
| Total Orders | Count of distinct order IDs | Do not count rows as orders unless each row is one order |
| Average Order Value | Total revenue ÷ distinct orders | Use the same scope and filters for numerator and denominator |
| Average Pizzas per Order | Total pizzas sold ÷ distinct orders | Requires valid quantity and order ID |
| Revenue Contribution % | Group revenue ÷ total revenue × 100 | Grouping must cover the same filtered dataset |

---

## 🧪 6. Assumptions to Confirm

**Do not treat these as verified until the data has been inspected.**

| ID | Assumption | Status |
|---|---|---|
| A-1 | The provided CSV/XLSX represents the intended analysis period | Unconfirmed |
| A-2 | The order identifier uniquely identifies an order | Unconfirmed |
| A-3 | Quantity and price fields are numeric and use consistent units | Unconfirmed |
| A-4 | The revenue field, if present, has a known definition | Unconfirmed |
| A-5 | Dates and times can be parsed consistently | Unconfirmed |
| A-6 | Product category and size labels are standardized or can be normalized transparently | Unconfirmed |

---

## 🚧 7. Constraints and Limitations

- Conclusions are limited to the fields and time period in the dataset.
- Descriptive patterns do not prove causation.
- Profitability cannot be calculated reliably without cost data.
- Customer behavior beyond order/product/time patterns requires appropriate customer-level fields.
- Inventory and staffing recommendations are **indicative only** unless inventory, staffing, and service data are available.

Out-of-scope items are listed in [`Business-Problem.md`](Business-Problem.md#-62-out-of-scope-unless-additional-data-is-supplied).

---

## 📌 8. Established Decisions

| ID | Decision | Where applied |
|---|---|---|
| D-1 | Total Orders is counted with distinct order IDs, never row counts (unless each row is verified to be one order) | KPI K2, FR-08 |
| D-2 | AOV is computed from aggregate revenue ÷ distinct orders, never by averaging row-level prices | KPI K4, FR-09 |
| D-3 | Low-performing products are identified separately for each metric (revenue, quantity) | FR-17, Question 17 |
| D-4 | The project is descriptive; no causal, profitability, or forecasting claims without additional data | §7, Problem §6.2 |
| D-5 | Unavailable fields are recorded as unavailable, not estimated | README data note |

---

## ✅ 9. Acceptance Criteria

The business-analysis stage is ready to move forward when:

- [ ] The business problem and objectives are written in plain language.
- [ ] Scope and out-of-scope items are documented.
- [ ] Each KPI has a formula and interpretation.
- [ ] Business questions are mapped to data fields and analysis outputs.
- [ ] Dataset grain and required columns have been checked.
- [ ] Assumptions and limitations are recorded.
- [ ] There is a clear plan for validating results across tools.

---

## ❓ 10. Open Questions

Resolve these during data inspection and record the answers here and in §6.

| ID | Open question | Affects |
|---|---|---|
| OQ-1 | What are the exact column names and data types in the source file? | All files |
| OQ-2 | What does one row represent (the dataset grain)? | K2, K3, K5, FR-05 |
| OQ-3 | Is there a line-revenue field, or must revenue be computed as quantity × unit price? Do discounts, tax, or refunds apply? | K1, FR-06 |
| OQ-4 | Does the data include timestamps that support hourly analysis, and does it cover a complete period? | K10–K12, Questions 10 and 12 |
| OQ-5 | Is a customer identifier present? | Question 23, out-of-scope items |
| OQ-6 | How should zero-order scopes be handled when computing AOV and Average Pizzas per Order? | K4, K5 |
| OQ-7 | Which currency and rounding convention apply to monetary KPIs? | KPI quality checklist |
| OQ-8 | Do the reported row/column counts and year match the file? | README dataset profile |

> **Important:** These questions should remain open until the actual dataset in Folder 02 has been inspected. Do not infer or assume answers from the project documentation alone.

---

## 🔍 11. Dataset Validation

The open questions, assumptions, and data-related requirements in this document will be validated against the actual dataset in Folder 02 before analysis and implementation begin.

The dataset inspection will confirm:

- Exact schema and column names
- Data types
- Row grain
- Revenue and sales fields
- Quantity and price fields
- Timestamp/date fields
- Customer identifier availability
- Product, category, size, and order identifiers
- Currency and monetary conventions
- Actual row and column counts
- Analysis period covered by the dataset
- Missing values and duplicates
- Invalid or inconsistent records relevant to the analysis
- Any data-quality issues that may affect KPI calculations

The results of this validation should be used to update the relevant assumptions and open questions in this document.

---

## 🔗 12. Requirement Traceability

This mapping connects the business requirements to the KPIs, analysis activities, and future implementation deliverables. It provides a clear path from **business requirement → KPI / analysis → implementation → final output**.

| Requirement / Business Area | KPI / Analysis | Future Implementation |
|---|---|---|
| Overall sales performance | K1–K5 | SQL / Python / Dashboard |
| Time patterns | K10–K12 | SQL / Python / Dashboard |
| Product performance | K6–K9 | SQL / Python / Dashboard |
| Order behavior | K2, K5, K9 | SQL / Python |
| Business recommendations | All relevant KPIs | Final Report |

### 12.1 Detailed Requirement Mapping

| Requirement | Related KPI / Analysis | Future Implementation |
|---|---|---|
| BR-01 — Overall sales performance | K1–K5 | SQL / Python / Dashboard |
| BR-02 — Order volume and pizza quantity | K2, K3, K5 | SQL / Python / Dashboard |
| BR-03 — Average order value | K4 | SQL / Python / Dashboard |
| BR-04 — Performance over time | K10–K12 | SQL / Python / Dashboard |
| BR-05 — Product group comparison | K6–K8 | SQL / Python / Dashboard |
| BR-06 — Top and bottom products | K7–K9 | SQL / Python / Dashboard |
| BR-07 — Evidence-based decisions | All relevant KPIs | Final Report |
| BR-08 — Data trust and validation | Data validation + KPI reconciliation | SQL / Python |
| BR-09 — Efficient navigation | Dashboard filters, labels, and visual structure | Dashboard |
| BR-10 — Reproducibility | Saved SQL, Python scripts, workbooks, and documented methods | SQL / Python / Documentation |

### 12.2 Functional Requirement Mapping

| Requirement Area | Functional Requirements | KPI / Analysis | Future Implementation |
|---|---|---|---|
| Data loading and validation | FR-01–FR-05 | Dataset profiling, grain, data-quality checks | SQL / Python |
| Core KPI analysis | FR-06–FR-10 | K1–K5 | SQL / Python / Dashboard |
| Time analysis | FR-11–FR-13 | K10–K12 | SQL / Python / Dashboard |
| Product analysis | FR-14–FR-17 | K6–K9 | SQL / Python / Dashboard |
| Reporting | FR-18–FR-20 | Findings, recommendations, KPI interpretation | Dashboard / Final Report |

### 12.3 Existing Implementation Locations

The following paths are the **intended** implementation locations. Confirm that they exist in the repository before linking to them.

| Requirement area | Main implementation location |
|---|---|
| Data loading and validation | `03_SQL/01_Data_Import.sql`, `03_SQL/02_Data_Validation.sql`, Python data-cleaning files |
| Core KPIs | `03_SQL/03_KPI_Analysis.sql`, dashboard KPI cards |
| Sales trends | `03_SQL/04_Sales_Trend_Analysis.sql`, time-trend visuals |
| Product performance | `03_SQL/05_Product_Analysis.sql`, product/category/size visuals |
| Findings and actions | `08_Insights_and_Recommendations/` |
| Final communication | Dashboards and final report |

The question-level mapping is in [`Business-Questions.md`](Business-Questions.md#-question-to-analysis-map).

---

## 🔄 13. Traceability Workflow

The intended project flow is:

**Business Requirements**
→ **Dataset Validation**
→ **KPI Definitions**
→ **Business Questions**
→ **SQL / Python Analysis**
→ **Dashboard**
→ **Findings & Recommendations**
→ **Final Report**

Each stage should be traceable back to the requirements defined in this document.

This ensures that the final analysis and dashboard address the original business needs rather than introducing unrelated metrics or visuals.
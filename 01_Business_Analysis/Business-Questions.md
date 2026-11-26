# 🍕 Business Questions — Pizza Sales Analysis

> Part of [`01_Business_Analysis`](README.md). Related: [Problem](Business-Problem.md) · [Requirements](Business-Requirements.md) · [KPIs](KPIs.md)

## 🎯 Purpose

These questions turn the business problem into a practical analysis checklist. Answer them with **validated data** and record the SQL query, chart, or report section that supports each answer.

If a question cannot be supported by the available data, record why instead of answering it.

> **This document defines the questions, not their answers. Do not fill in results before running and validating the analysis.**

KPI IDs (K1–K12) refer to [`KPIs.md`](KPIs.md).

---

## 🔗 Question → KPI → Analysis → Dashboard

This mapping connects the business questions to the metrics, technical analysis, and final reporting layer.

| Question | KPI | Analysis | Dashboard / Output |
|---|---|---|---|
| What is the total recorded revenue for the full analysis period? | K1 | KPI Analysis | KPI Card |
| How many distinct orders were placed? | K2 | KPI Analysis | KPI Card |
| How many pizzas were sold? | K3 | KPI Analysis | KPI Card |
| What is the average order value? | K4 | KPI Analysis | KPI Card |
| How many pizzas are sold per order on average? | K5 | KPI Analysis | KPI Card |
| Which pizza categories generate the most and least revenue? | K6 | Product Analysis | Category Bar Chart |
| Which individual pizza types generate the most revenue? | K7 | Product Analysis | Ranked Bar Chart |
| Which pizza types sell the greatest quantity? | K8 | Product Analysis | Ranked Bar Chart |
| Which products have the lowest revenue or quantity? | K7 / K8 / K9 | Product Analysis | Product Table |
| How does revenue change by day or date? | K10 | Sales Trend Analysis | Line Chart |
| Which weekdays have the highest and lowest revenue? | K10 | Sales Trend Analysis | Weekday Bar Chart |
| Which weekdays have the highest and lowest order counts? | K11 | Sales Trend Analysis | Weekday Bar Chart |
| At what hours is order activity highest and lowest? | K12 | Sales Trend Analysis | Hourly Chart |
| Are there visible peaks, dips, or recurring patterns? | K10–K12 | Sales Trend Analysis | Trend Dashboard |
| Do the headline KPIs reconcile across tools? | K1–K12 | Data Validation | Validation Table |
| How much revenue comes from each category, size, or product? | K6–K9 | Product Analysis | Contribution Chart |
| How many orders contain each product, category, or size? | K2 / K7–K9 | Product / Order Analysis | Comparison Chart |
| What is the distribution of pizzas per order? | K5 | Order Behavior Analysis | Distribution Chart / Table |
| Can customer-level behavior be analyzed? | — | Data Availability / Validation | Data Limitation Note |
| What findings are useful to management? | K1–K12 | Insight Analysis | Insight Cards / Summary |
| What do peak periods imply for staffing or preparation? | K10–K12 | Trend Analysis | Operations Insight |
| What inventory hypotheses can be formed? | K3 / K8 | Product Analysis | Inventory Insight |
| What additional data is required? | — | Gap Analysis | Data Request Table |

> **Note:** KPI assignments should be confirmed against [`KPIs.md`](KPIs.md) before implementation. If the KPI definitions or IDs change, update this mapping accordingly.

---

## 📊 A. Overall Sales Performance (K1–K5)

### 1. What is the total recorded revenue for the full analysis period?
**KPI:** K1

### 2. How many distinct orders were placed?
**KPI:** K2

### 3. How many pizzas were sold?
**KPI:** K3

### 4. What is the average order value?
**KPI:** K4

### 5. How many pizzas are sold per order on average?
**KPI:** K5

### 6. Do the headline KPIs reconcile across SQL, Excel, Power BI, and Tableau?
**KPI:** K1–K5

**Suggested outputs:** KPI cards, KPI summary table, cross-tool validation checks.

---

## 📈 B. Sales Over Time (K10–K12)

### 7. How does revenue change by day or date?
**KPI:** K10

### 8. Which weekdays have the highest and lowest revenue?
**KPI:** K10

### 9. Which weekdays have the highest and lowest order counts?
**KPI:** K11

### 10. At what hours is order activity highest and lowest, if timestamps support hourly analysis?
**KPI:** K12

### 11. Are there visible peaks, dips, or recurring patterns across the available period?
**KPI:** K10–K12

### 12. Is the dataset period complete enough to support a fair comparison between days and time periods?
**KPI:** Validation / data-quality check

**Suggested outputs:** line chart for daily revenue; weekday bar chart; hourly order/revenue chart if available; period-completeness validation.

---

## 🍕 C. Product and Menu Performance (K6–K9)

### 13. Which pizza categories generate the most and least revenue?
**KPI:** K6

### 14. Which pizza sizes generate the most and least revenue?
**KPI:** K6

### 15. Which individual pizza types generate the most revenue?
**KPI:** K7

### 16. Which pizza types sell the greatest quantity?
**KPI:** K8

### 17. Which products have the lowest revenue or quantity, and do both measures tell the same story?
**KPI:** K7 / K8 / K9

### 18. How much of total revenue comes from each category, size, or product?
**KPI:** K6–K9

### 19. Are there products with high quantity but relatively low revenue, or high revenue with lower quantity?
**KPI:** K7–K9

**Suggested outputs:** ranked bar charts, contribution percentages, product comparison table, revenue-versus-quantity analysis.

---

## 🛒 D. Order Behavior (K2, K5, K9)

### 20. How many orders contain each product, category, or size?
**KPI:** K2 / K7–K9

### 21. What is the distribution of pizzas per order, if the data grain allows it?
**KPI:** K5

### 22. Do order counts and pizza quantities suggest different demand patterns?
**KPI:** K2 / K3 / K5

### 23. Can customer-level behavior be analyzed from the available fields, or is a customer identifier missing?
**KPI:** Not applicable

> **Customer-level analysis should only be performed if the required customer identifier and relevant fields exist in the dataset. Order-level data should not be presented as customer-level behavior.**

**Suggested outputs:** order-count comparison, quantity/order analysis, order-size distribution, data-availability note.

---

## 💡 E. Business Interpretation

### 24. Which findings are large enough to be useful to management?
**KPI:** K1–K12, depending on the finding

### 25. Which findings are stable patterns versus one-off changes?
**KPI:** K10–K12

### 26. What menu, promotion, or merchandising experiments could be tested based on the evidence?
**KPI:** K6–K9

### 27. What do observed peak periods imply for staffing or preparation planning?
**KPI:** K10–K12

### 28. What inventory-planning hypotheses can be formed from quantity patterns, and what additional stock data would be needed?
**KPI:** K3 / K8

### 29. What extra data would be needed to analyze profit, discounts, customer retention, marketing effectiveness, or stockouts?
**KPI:** Not applicable — data gap analysis

**Suggested outputs:** insight statements, recommendation table, limitations, assumptions, and next-step data requests.

> **Important:** Business recommendations should be evidence-linked. The analysis may identify a pattern or hypothesis, but it should not claim causation unless the available data supports it.

---

## 🧭 Question-to-Analysis Map

Paths are the intended implementation locations. **Confirm that they exist in the repository before linking to or referencing them as completed analyses.**

| Question Group | Main Fields Needed | Analysis Location | Expected Output |
|---|---|---|---|
| A. Overall KPIs | Revenue/price, quantity, order ID | `03_SQL/03_KPI_Analysis.sql` | KPI summary |
| B. Time patterns | Date/time, revenue, order ID, quantity | `03_SQL/04_Sales_Trend_Analysis.sql` | Time-based comparisons |
| C–D. Product performance and order behavior | Product/type, category, size, revenue, quantity, order ID | `03_SQL/05_Product_Analysis.sql` | Ranked products and group comparisons |
| Data reliability | All relevant fields | `03_SQL/02_Data_Validation.sql` and Python checks | Validation notes |
| E. Recommendations | Results from analyses plus business context | `08_Insights_and_Recommendations/` | Evidence-linked actions |

---

## 📊 Dashboard Mapping

The final dashboard should communicate the most decision-relevant findings from the analysis.

| Dashboard Section | Business Questions | Primary KPI / Measure | Recommended Visual |
|---|---|---|---|
| Executive Overview | Q1–Q6 | K1–K5 | KPI Cards |
| Revenue Trend | Q7–Q12 | K10 | Line Chart |
| Weekday Performance | Q8–Q9 | K10–K11 | Bar Chart |
| Hourly Demand | Q10–Q11 | K12 | Hour / Time Chart |
| Category Performance | Q13, Q18 | K6 | Bar / Contribution Chart |
| Product Performance | Q15–Q19 | K7–K9 | Ranked Bar Chart |
| Order Behavior | Q20–Q23 | K2–K5 | Distribution / Comparison Chart |
| Business Insights | Q24–Q29 | Relevant KPIs | Insight Cards / Table |
| Data Quality | Q6, Q12, Q23, Q29 | Validation checks | Validation / Limitation Table |

> **Dashboard design should follow the analysis. Do not create visuals simply because a chart type is available. Each visual should answer a defined business question or support a clearly stated business decision.**

---

## 🔍 Analysis and Validation Principles

The following rules apply when answering the questions:

1. **Use validated data.**
   - Check duplicates, nulls, invalid values, date ranges, and unexpected categories before interpreting results.

2. **Respect the dataset grain.**
   - Confirm whether each row represents an order, order line, pizza, or another business event before calculating metrics.

3. **Use consistent KPI definitions.**
   - The same KPI should produce the same result across SQL, Excel, Power BI, and Tableau unless a documented transformation explains the difference.

4. **Do not infer customer behavior from order data.**
   - Customer-level conclusions require a reliable customer identifier.

5. **Distinguish correlation from causation.**
   - A sales pattern does not automatically prove why the pattern occurred.

6. **Separate observations from recommendations.**
   - First establish what the data shows; then determine what action may be justified.

7. **Document limitations.**
   - If the dataset lacks profit, discount, customer, inventory, marketing, or stockout information, state that explicitly.

8. **Record the evidence.**
   - Each completed answer should reference the SQL query, validation check, chart, dashboard page, or report section supporting the conclusion.

---

## 📝 How to Write an Answer to Each Question

For each question, record all seven elements:

| # | Element | Content |
|---|---|---|
| 1 | **Question** | The business question being answered |
| 2 | **Metric** | The measure used and its formula; reference the KPI ID where applicable |
| 3 | **Result** | The value or pattern observed in the validated dataset |
| 4 | **Evidence** | Query name, chart, table, dashboard page, or validation result |
| 5 | **Interpretation** | What the result may mean in a business context |
| 6 | **Action** | A realistic next step, if justified by the evidence |
| 7 | **Limitation** | What the data cannot establish or what assumptions apply |

### Example Answer Structure

> **Question:** What is the total recorded revenue for the full analysis period?
>
> **Metric:** K1 — Total Revenue
>
> **Result:** Record the validated result after running the SQL analysis.
>
> **Evidence:** Reference the KPI SQL query and corresponding dashboard KPI card.
>
> **Interpretation:** Explain what the result indicates about overall sales performance.
>
> **Action:** Identify an appropriate management action only if supported by the evidence.
>
> **Limitation:** State any relevant data-quality, period, or definition limitations.

---

## 📌 Final Traceability Chain

The completed analysis should maintain the following traceability:

```text
Business Problem
      ↓
Business Requirement
      ↓
Business Question
      ↓
KPI / Metric
      ↓
Data Fields
      ↓
SQL / Python Analysis
      ↓
Validation
      ↓
Power BI / Tableau Visual
      ↓
Business Insight
      ↓
Recommendation / Decision

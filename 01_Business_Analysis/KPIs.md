# 🍕 KPI Dictionary — Pizza Sales Analysis

> Part of [`01_Business_Analysis`](README.md). Related: [Problem](Business-Problem.md) · [Requirements](Business-Requirements.md) · [Questions](Business-Questions.md)

## 📖 How to Use This Document

Treat this file as the **source of truth for KPI names and formulas**. Before implementing a measure in SQL, Excel, Power BI, or Tableau, confirm the source columns and update any definition that differs from the project brief. The definitions below are starting points that must be confirmed against the dataset and project brief.

> ⚠️ **Important:** The column names shown in formulas are **logical placeholders**. They must be mapped to the actual dataset schema before SQL, Python, Excel, Power BI, or Tableau implementation.

Examples of placeholder column names include:

- `line_revenue`
- `quantity`
- `unit_price`
- `order_id`

Do **not** assume these names exist in the source dataset. Confirm the actual schema first and document any mapping where necessary.

## 📊 Core KPIs

| ID | KPI | Business meaning | Formula | Unit | Cautions |
|---|---|---|---|---|---|
| K1 | **Total Revenue** | Total recorded sales value for the selected scope | `SUM(line_revenue)`; if no line-revenue field exists, `SUM(quantity * unit_price)` — only after confirming this represents the intended sales amount | Currency units used by the source data | Revenue is **not** profit. Check whether discounts, tax, refunds, or adjustments are included. |
| K2 | **Total Orders** | Number of distinct orders placed in the selected scope | `COUNT(DISTINCT order_id)` | Orders | An order can contain multiple pizza line items; counting rows may overstate order count. Do not count rows as orders unless each row is one order. |
| K3 | **Total Pizzas Sold** | Total number of pizzas represented by the quantity field | `SUM(quantity)` | Pizzas | Confirm whether quantity represents individual pizzas or another unit, and what each row means. |
| K4 | **Average Order Value (AOV)** | Average recorded revenue per order | `Total Revenue / Total Orders` | Currency units per order | Do not average row-level prices. Compute from aggregate revenue and distinct orders over the **same scope and filters**. Define handling for zero orders. |
| K5 | **Average Pizzas per Order** | Average quantity of pizzas associated with each order | `Total Pizzas Sold / Total Orders` | Pizzas per order | Describes order composition only; it does not measure customer satisfaction. Requires valid quantity and order ID. |

## 🥧 Product and Contribution Measures

| ID | KPI | Formula | Unit | Use | Cautions |
|---|---|---|---|---|---|
| K6 | **Revenue by Product / Category / Size** | Sum revenue for each group | Currency units | Compare sales contribution across product groups | More revenue ≠ more profitable. |
| K7 | **Quantity Sold by Product / Category / Size** | Sum quantity for each group | Pizzas | Shows volume independently from revenue | — |
| K8 | **Revenue Contribution %** | `(Revenue for selected group / Total Revenue for the same filtered scope) * 100` | Percent | Show each group's share of total revenue | Groups must cover the same filtered dataset. Contributions should total ≈100% when groups are mutually exclusive and cover the full scope. |
| K9 | **Order Count by Product / Category / Size** | Count distinct orders containing the group | Orders containing the group | Compare how widely a group appears in orders | An order containing two categories is counted in both, so category-level order counts **may not add up to total orders**. |

## 🕒 Time-Based Measures

| ID | KPI | Formula | Unit | Use | Cautions |
|---|---|---|---|---|---|
| K10 | **Revenue by Date / Weekday / Hour** | Sum revenue grouped by the selected time dimension | Currency units per time group | Identify observed peaks, dips, and recurring patterns | Check whether the dataset covers a complete period and whether all days/hours are represented. |
| K11 | **Orders by Date / Weekday / Hour** | Count distinct order IDs within each time group | Orders | Demand-pattern analysis and staffing discussions | If order timestamps are absent or incomplete, **do not infer hourly demand**. |
| K12 | **Quantity by Date / Weekday / Hour** | Sum quantity within each time group | Pizzas | Demand and stock-planning discussions | Subject to inventory data limitations. |

## 🔗 KPI → Business Question Mapping

Use this mapping to make the relationship between the KPI dictionary and the business-question document explicit.

| KPI | Supports |
|---|---|
| K1 — Total Revenue | BQ-01 |
| K2 — Total Orders | BQ-02 |
| K3 — Total Pizzas Sold | BQ-03 |
| K4 — Average Order Value | BQ-04 |
| K5 — Average Pizzas per Order | BQ-05 |
| K6 — Revenue by Product / Category / Size | Product questions |
| K7 — Quantity Sold by Product / Category / Size | Product questions |
| K8 — Revenue Contribution % | Product questions |
| K9 — Order Count by Product / Category / Size | Product questions |
| K10 — Revenue by Date / Weekday / Hour | Time questions |
| K11 — Orders by Date / Weekday / Hour | Time questions |
| K12 — Quantity by Date / Weekday / Hour | Time questions |

> **Note:** The BQ-01 to BQ-05 mappings should match the exact IDs and wording used in [`Business-Questions.md`](Business-Questions.md). If the business-question document uses different IDs, update this table rather than creating new question IDs here.

## ✅ KPI Quality Checklist

Before publishing any KPI, confirm:

- [ ] Source field(s) are known and correctly typed.
- [ ] Placeholder column names have been mapped to the actual dataset schema.
- [ ] The formula matches the definition above.
- [ ] The time period and filters are clear.
- [ ] Nulls, duplicates, and invalid records have been considered.
- [ ] SQL and dashboard results reconcile.
- [ ] Currency units and rounding are clear.
- [ ] The interpretation does not claim more than the metric supports.

## 🔖 Naming Conventions

Use these labels consistently across all tools:

- `Total Revenue`
- `Total Orders`
- `Total Pizzas Sold`
- `Average Order Value`
- `Average Pizzas per Order`
- `Revenue Contribution %`

If the business brief requires a different definition, document the change in this file before using it elsewhere.
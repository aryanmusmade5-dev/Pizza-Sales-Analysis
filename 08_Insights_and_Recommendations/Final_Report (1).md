# Final Report — Pizza Sales Analysis

> End-to-end business analytics project: **SQL · Python · Excel · Power BI · Tableau**
> Dataset: `pizza_sales.csv` · 48,620 transaction records · 21,350 orders

## Table of Contents

1. [Executive Summary](#1-executive-summary)
2. [Business Problem](#2-business-problem)
3. [Business Objectives](#3-business-objectives)
4. [Data Source](#4-data-source)
5. [Tools and Workflow](#5-tools-and-workflow)
6. [Key Performance Indicators](#6-key-performance-indicators)
7. [Major Business Insights](#7-major-business-insights)
8. [Recommendations](#8-recommendations)
9. [Dashboard Solutions](#9-dashboard-solutions)
10. [Business Decisions Supported](#10-business-decisions-supported)
11. [Limitations](#11-limitations)
12. [Conclusion and Next Steps](#12-conclusion-and-next-steps)
13. [Repository Structure](#13-repository-structure)

---

## 1. Executive Summary

This project analyzes transactional sales data from a pizza store to evaluate business performance, product trends, and improvement opportunities. It follows a complete workflow from raw data to dashboards and business recommendations.

**Headline results**

| Metric | Result |
|---|---:|
| Total Revenue | **$817,860.05** |
| Total Orders | **21,350** |
| Total Pizzas Sold | **49,574** |
| Average Order Value | **$38.31** |

**Key findings**
- **Classic** is the top category (26.9% of revenue).
- **Large** is the top size (45.9% of revenue).
- **The Thai Chicken Pizza** is the top product ($43,434.25).
- **Friday** is the strongest day; **July** is the strongest month.

The results support decisions on **sales, marketing, menu optimization, inventory, staffing, and KPI monitoring**.

---

## 2. Business Problem

Without structured analysis, it is hard for the business to see:

- Overall revenue, order, and volume performance
- Strong and weak categories, sizes, and products
- Sales patterns across days, months, and hours
- Opportunities for menu and operational improvement

This project addresses these gaps through data analysis and interactive dashboards.

---

## 3. Business Objectives

1. Identify total revenue, pizzas sold, and orders.
2. Determine sales distribution by category, size, and product.
3. Analyze time-based sales trends.
4. Identify best- and worst-selling pizzas.
5. Calculate Average Order Value and Average Pizzas per Order.
6. Provide dashboards for effective decision-making.

These objectives come from the project's Business Requirements Document (BRD).

---

## 4. Data Source

**Dataset:** `pizza_sales.csv` (**48,620** transaction records, one row per order line item)

| Field | Description |
|---|---|
| `order_id` | Order identifier |
| `pizza_id` | Pizza variant identifier |
| `pizza_name` | Product name |
| `quantity` | Pizzas in the line item |
| `order_date` | Date of the order |
| `unit_price` | Price per pizza |
| `total_price` | Line-item revenue |
| `pizza_size` | S, M, L, XL, XXL |
| `pizza_category` | Classic, Supreme, Chicken, Veggie |
| `pizza_ingredients` | Ingredients list |

---

## 5. Tools and Workflow

| Tool | Purpose |
|---|---|
| **SQL** | Querying and analyzing sales data |
| **Python** | Data analysis and exploration |
| **Excel** | Spreadsheet analysis and dashboard |
| **Power BI** | Interactive BI dashboard |
| **Tableau** | Interactive visualization dashboards |

```text
Business Requirements → Data Collection → Data Preparation
        → SQL Analysis → Python Analysis
        → Excel / Power BI / Tableau Dashboards
        → Business Insights → Recommendations → Final Report
```

---

## 6. Key Performance Indicators

| KPI | Definition | Result |
|---|---|---:|
| Total Revenue | Sum of `total_price` | **$817,860.05** |
| Total Pizzas Sold | Sum of `quantity` | **49,574** |
| Total Orders | Count of unique `order_id` | **21,350** |
| Average Order Value | Total Revenue ÷ Total Orders | **$38.31** |
| Average Pizzas per Order | Total Pizzas Sold ÷ Total Orders | **2.32** |

---

## 7. Major Business Insights

> Full detail: [Business Insights](Business_Insights.md)

### 7.1 Category Performance

| Category | Revenue | Share | Quantity |
|---|---:|---:|---:|
| **Classic** | $220,053.10 | 26.9% | 14,888 |
| Supreme | $208,197.00 | 25.5% | 11,987 |
| Chicken | $195,919.50 | 24.0% | 11,050 |
| Veggie | $193,690.45 | 23.7% | 11,649 |

Classic leads on revenue and quantity, but the four categories are closely balanced.

### 7.2 Size Performance

| Size | Revenue | Share | Quantity |
|---|---:|---:|---:|
| **Large** | $375,318.70 | 45.9% | 18,956 |
| Medium | $249,382.25 | 30.5% | 15,635 |
| Small | $178,076.50 | 21.8% | 14,403 |
| XL | $14,076.00 | 1.7% | 552 |
| XXL | $1,006.60 | 0.1% | 28 |

Large generates nearly half of all revenue; XL and XXL are marginal.

### 7.3 Top and Bottom Products

| Top 5 by Revenue | Revenue | Bottom 5 by Revenue | Revenue |
|---|---:|---|---:|
| The Thai Chicken Pizza | $43,434.25 | The Brie Carre Pizza | $11,588.50 |
| The Barbecue Chicken Pizza | $42,768.00 | The Green Garden Pizza | $13,955.75 |
| The California Chicken Pizza | $41,409.50 | The Spinach Supreme Pizza | $15,277.75 |
| The Classic Deluxe Pizza | $38,180.50 | The Mediterranean Pizza | $15,360.50 |
| The Spicy Italian Pizza | $34,831.25 | The Spinach Pesto Pizza | $15,596.00 |

Low performers should be reviewed with cost and profitability data before any menu-removal decision.

### 7.4 Time-Based Performance

- **Day of week:** Friday is strongest at **$136,073.90**; Sunday is weakest at **$99,203.50** (Friday is ~37% higher).
- **Month:** July is strongest at **$72,557.90**; October is weakest at **$64,027.60** (July is ~13% higher).

---

## 8. Recommendations

> Full detail: [Recommendations](Recommendations.md)

| Area | Key Recommendation |
|---|---|
| **Sales & Marketing** | Promote top products and bundles; measure campaigns against a baseline. |
| **Menu** | Review low performers using cost, profitability, and feedback before removal. |
| **Inventory** | Prioritize ingredients for high-volume products and Large pizzas. |
| **Staffing** | Plan for Thursday–Saturday demand, especially Friday. |
| **KPI Monitoring** | Track the five core KPIs weekly or monthly against prior periods. |

---

## 9. Dashboard Solutions

| Platform | Coverage |
|---|---|
| **Excel** | Spreadsheet-based KPI and sales analysis |
| **Power BI** | Interactive KPI and product-performance dashboard |
| **Tableau** | KPIs, category sales, monthly order trends, orders by hour, Top 5 and Bottom 5 pizzas |

---

## 10. Business Decisions Supported

| Decision | Supporting Analysis |
|---|---|
| Improve sales performance | Revenue, orders, pizzas sold |
| Plan staffing | Day and time-based demand |
| Optimize menu | Product and category performance |
| Plan inventory | Quantity by category, size, and product |
| Improve promotions | High-performing products and periods |
| Monitor performance | KPI dashboards |

---

## 11. Limitations

- The dataset has **no complete cost data**, so revenue must not be treated as profit.
- Sales data alone **cannot prove** that promotions caused changes in sales.
- There is **no customer identifier**, so customer-level behavior cannot be analyzed.
- Product decisions should also weigh profitability and customer feedback, not sales volume alone.

---

## 12. Conclusion and Next Steps

The analysis identifies **Classic** as the strongest category, **Large** as the strongest size, and the products and periods that contribute most and least to sales. These results give management a factual base for promotion, menu, inventory, and staffing decisions.

**Recommended next steps**
1. Continue monitoring the core KPIs through the dashboards.
2. Add **profit margin and ingredient cost** data to evaluate products on profitability.
3. Add **promotion campaign** data to measure promotional impact.
4. Collect **customer feedback** to support menu decisions.

---

## 13. Repository Structure

```text
01_Business_Analysis/
02_Data/
03_SQL/
04_Python/
05_Excel/
06_Power_BI/
07_Tableau/
08_Insights_and_Recommendations/
09_Documentation/
```

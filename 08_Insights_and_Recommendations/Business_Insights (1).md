# Business Insights — Pizza Sales Analysis

> **Scope:** Descriptive findings from `pizza_sales.csv`, aligned with the project's Business Requirements Document (BRD).
> **Supports decisions on:** sales performance, product strategy, menu optimization, inventory, staffing, and marketing.

## Table of Contents

1. [Overall Sales Performance](#1-overall-sales-performance)
2. [Pizza Category Performance](#2-pizza-category-performance)
3. [Pizza Size Performance](#3-pizza-size-performance)
4. [Top-Performing Pizzas](#4-top-performing-pizzas)
5. [Lowest-Performing Pizzas](#5-lowest-performing-pizzas)
6. [Day-of-Week Performance](#6-day-of-week-performance)
7. [Monthly Performance](#7-monthly-performance)
8. [Key Takeaways](#8-key-takeaways)
9. [Interpretation Notes](#9-interpretation-notes)

---

## 1. Overall Sales Performance

The dataset contains **48,620 transaction records** (order line items), representing **21,350 unique orders**.

| KPI | Result |
|---|---:|
| Total Revenue | **$817,860.05** |
| Total Pizzas Sold | **49,574** |
| Total Orders | **21,350** |
| Average Order Value (AOV) | **$38.31** |
| Average Pizzas per Order | **2.32** |

**Insight:** The business generated about **$817.9K** from 21,350 orders. With an average of 2.32 pizzas per order, customers typically buy multiple pizzas rather than a single one.

---

## 2. Pizza Category Performance

| Category | Revenue | Share of Revenue | Pizzas Sold |
|---|---:|---:|---:|
| **Classic** | $220,053.10 | 26.9% | 14,888 |
| Supreme | $208,197.00 | 25.5% | 11,987 |
| Chicken | $195,919.50 | 24.0% | 11,050 |
| Veggie | $193,690.45 | 23.7% | 11,649 |

**Insight:**
- **Classic** leads on both revenue and quantity sold.
- The four categories are closely balanced: the gap between first (Classic) and last (Veggie) is about **$26.4K**, or 3.2 percentage points of revenue share.
- Revenue is not concentrated in a single category, so category mix is a lever for promotion rather than a dependency risk.

---

## 3. Pizza Size Performance

| Size | Revenue | Share of Revenue | Pizzas Sold |
|---|---:|---:|---:|
| **Large (L)** | $375,318.70 | 45.9% | 18,956 |
| Medium (M) | $249,382.25 | 30.5% | 15,635 |
| Small (S) | $178,076.50 | 21.8% | 14,403 |
| X-Large (XL) | $14,076.00 | 1.7% | 552 |
| XX-Large (XXL) | $1,006.60 | 0.1% | 28 |

**Insight:**
- **Large** is the strongest size by both revenue and quantity, contributing nearly half of all revenue.
- Large, Medium, and Small together account for about **98%** of revenue.
- **XL and XXL** are marginal (about 1.8% of revenue combined), which makes their menu role worth reviewing.

---

## 4. Top-Performing Pizzas

Top five pizzas by revenue:

| Rank | Pizza | Revenue | Quantity |
|---:|---|---:|---:|
| 1 | **The Thai Chicken Pizza** | $43,434.25 | 2,371 |
| 2 | The Barbecue Chicken Pizza | $42,768.00 | 2,432 |
| 3 | The California Chicken Pizza | $41,409.50 | 2,370 |
| 4 | The Classic Deluxe Pizza | $38,180.50 | 2,453 |
| 5 | The Spicy Italian Pizza | $34,831.25 | 1,924 |

**Insight:**
- **The Thai Chicken Pizza** is the highest-revenue product.
- Three of the top five are Chicken pizzas, even though Chicken ranks third as a category. Product-level strength does not always follow category-level ranking.
- The Classic Deluxe Pizza has the highest quantity sold in this group (2,453), while Thai Chicken leads on revenue, which points to a price-point difference.

---

## 5. Lowest-Performing Pizzas

Bottom five pizzas by revenue:

| Rank | Pizza | Revenue | Quantity |
|---:|---|---:|---:|
| 1 | **The Brie Carre Pizza** | $11,588.50 | 490 |
| 2 | The Green Garden Pizza | $13,955.75 | 997 |
| 3 | The Spinach Supreme Pizza | $15,277.75 | 950 |
| 4 | The Mediterranean Pizza | $15,360.50 | 934 |
| 5 | The Spinach Pesto Pizza | $15,596.00 | 970 |

**Insight:**
- **The Brie Carre Pizza** is the lowest performer on both revenue and quantity.
- Low sales alone do not justify removal. Pricing, ingredient cost, profitability, promotion history, and customer feedback should be reviewed first (see [Recommendations](Recommendations.md)).

---

## 6. Day-of-Week Performance

| Day | Revenue | Share of Revenue |
|---|---:|---:|
| **Friday** | $136,073.90 | 16.6% |
| Thursday | $123,528.50 | 15.1% |
| Saturday | $123,182.40 | 15.1% |
| Wednesday | $114,408.40 | 14.0% |
| Tuesday | $114,133.80 | 14.0% |
| Monday | $107,329.55 | 13.1% |
| **Sunday** | $99,203.50 | 12.1% |

**Insight:**
- **Friday** is the strongest day, about **37% higher** than the weakest day, **Sunday**.
- Demand peaks from **Thursday to Saturday**, which is the window that matters most for staffing, preparation, and inventory.

---

## 7. Monthly Performance

| Position | Month | Revenue |
|---|---|---:|
| Highest | **July** | $72,557.90 |
| 2nd highest | May | $71,402.75 |
| 3rd highest | March | $70,397.10 |
| Lowest | **October** | $64,027.60 |

**Insight:**
- Monthly revenue varies noticeably: July is about **13% higher** than October.
- These patterns can guide seasonal planning and promotion timing.

> **Note:** The BRD links higher summer sales to promotional campaigns. This analysis reports the observed values but does **not** establish that promotions caused the increase. Campaign-level data would be needed to test that.

---

## 8. Key Takeaways

| Area | Takeaway |
|---|---|
| **Sales** | About $817.9K revenue from 21,350 orders at an AOV of $38.31. |
| **Category** | Classic leads, but categories are closely balanced. |
| **Size** | Large contributes ~46% of revenue; XL/XXL are marginal. |
| **Top product** | The Thai Chicken Pizza has the highest revenue. |
| **Weakest product** | The Brie Carre Pizza has the lowest revenue and quantity. |
| **Day** | Friday is strongest; Sunday is weakest. |
| **Month** | July is strongest; October is weakest. |

---

## 9. Interpretation Notes

- These are **descriptive** findings from sales data, not causal conclusions.
- **Revenue is not profit.** The dataset has no complete cost information.
- Low sales do not automatically mean a product should be discontinued.
- Decisions should combine these findings with profitability, ingredient cost, promotions, customer feedback, and operational constraints.

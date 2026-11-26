# Recommendations — Pizza Sales Analysis

> Actions derived from the findings in [Business Insights](Business_Insights.md). Each recommendation lists the supporting evidence, suggested actions, and the metric to track.

## Table of Contents

1. [Priority Summary](#1-priority-summary)
2. [Strengthen High-Performing Products](#2-strengthen-high-performing-products)
3. [Protect the Classic Category](#3-protect-the-classic-category)
4. [Optimize the Size Strategy](#4-optimize-the-size-strategy)
5. [Review Low-Performing Products](#5-review-low-performing-products)
6. [Plan Staffing Around Demand](#6-plan-staffing-around-demand)
7. [Improve Inventory Planning](#7-improve-inventory-planning)
8. [Use Promotions Strategically](#8-use-promotions-strategically)
9. [Monitor KPIs Regularly](#9-monitor-kpis-regularly)
10. [Use Multiple Metrics for Menu Decisions](#10-use-multiple-metrics-for-menu-decisions)
11. [Expected Benefits](#11-expected-benefits)

---

## 1. Priority Summary

| Priority | Action | Business Area |
|---|---|---|
| **High** | Protect availability of top-performing products | Operations |
| **High** | Plan inventory around high-demand categories and sizes | Inventory |
| **High** | Staff for Thursday–Saturday demand, especially Friday | Staffing |
| **Medium** | Promote strong products and bundles | Marketing |
| **Medium** | Review low-performing products before any removal | Menu Strategy |
| **Medium** | Evaluate XL/XXL demand and economics | Product Strategy |
| **Ongoing** | Monitor KPIs through dashboards | Management |

---

## 2. Strengthen High-Performing Products

**Evidence:** The Thai Chicken ($43.4K), Barbecue Chicken ($42.8K), California Chicken ($41.4K), Classic Deluxe ($38.2K), and Spicy Italian ($34.8K) are the top five pizzas by revenue.

**Actions**
- Feature these pizzas prominently in promotions and use them as anchor items in campaigns.
- Test meal or bundle offers built around them.
- Monitor availability closely during high-demand periods.

**Track:** Revenue and quantity by product.

---

## 3. Protect the Classic Category

**Evidence:** Classic is the top category by revenue ($220.1K, 26.9%) and quantity (14,888).

**Actions**
- Keep sufficient inventory for popular Classic pizzas.
- Test bundles that pair Classic pizzas with complementary items.
- Use Classic as a benchmark when evaluating other categories.

**Track:** Category revenue share and quantity.

---

## 4. Optimize the Size Strategy

**Evidence:** Large pizzas generate about 46% of revenue. XL and XXL together generate about 1.8%.

**Actions**
- Ensure adequate Large-pizza inventory during high-demand periods.
- Test bundle or upsell offers that encourage Large selection.
- Review the economics of XL and XXL (ingredient use, preparation effort, menu space) before changing the assortment.

**Track:** Revenue and quantity by size.

---

## 5. Review Low-Performing Products

**Evidence:** The lowest-revenue products are The Brie Carre, Green Garden, Spinach Supreme, Mediterranean, and Spinach Pesto pizzas.

**Actions:** Evaluate each product on the following before any discontinuation decision:

| Factor | Question |
|---|---|
| Sales volume | Is demand consistently low or seasonal? |
| Selling price | Is pricing suppressing demand? |
| Ingredient cost & profitability | Is the product still margin-positive? |
| Customer feedback | Do loyal customers value it? |
| Promotion history | Has it been promoted fairly? |
| Menu placement | Is it visible to customers? |

Remove or redesign a product only when this broader evidence supports it.

**Track:** Revenue, quantity, and margin by product.

---

## 6. Plan Staffing Around Demand

**Evidence:** Friday is the highest-revenue day ($136.1K, ~37% above Sunday at $99.2K). Demand is strongest from Thursday to Saturday.

**Actions**
- Schedule additional staff and preparation capacity for Thursday–Saturday.
- Avoid overstaffing on lower-demand days such as Sunday and Monday.
- Review time-based demand in the dashboards before adjusting schedules.

**Track:** Orders and revenue by day and hour.

---

## 7. Improve Inventory Planning

**Evidence:** Demand is concentrated in specific categories, sizes, and products.

**Actions**
- Prioritize ingredients used in high-volume pizzas, especially popular Large pizzas.
- Reduce unnecessary stock for consistently low-volume products.
- Use sales trends to guide purchasing and preparation.

**Track:** Quantity sold by product and size against stock levels.

---

## 8. Use Promotions Strategically

**Actions**
- Promote high-performing products to protect and grow demand.
- Run targeted offers on weaker products to test whether they can be improved.
- Compare sales before and after each promotion to measure effectiveness.

> **Caveat:** The BRD associates summer sales with promotional campaigns, but sales data alone cannot prove causation. Use campaign-level data to measure promotional impact.

**Track:** Sales uplift versus a pre-campaign baseline.

---

## 9. Monitor KPIs Regularly

| KPI | Definition |
|---|---|
| Total Revenue | Sum of `total_price` |
| Total Pizzas Sold | Sum of `quantity` |
| Total Orders | Count of unique `order_id` |
| Average Order Value | Total Revenue ÷ Total Orders |
| Average Pizzas per Order | Total Pizzas Sold ÷ Total Orders |

**Actions**
- Review KPIs weekly or monthly in the Power BI, Tableau, or Excel dashboards.
- Compare against previous periods and investigate significant changes.

---

## 10. Use Multiple Metrics for Menu Decisions

Menu decisions should not rely on revenue alone:

```text
Revenue + Quantity Sold + Orders
+ Profitability + Ingredient Cost + Customer Feedback
                    ↓
            Final Menu Decision
```

This reduces the risk of removing products that have strategic value despite lower sales volume.

---

## 11. Expected Benefits

If implemented and monitored, these recommendations can help the business:

- Improve sales performance and promotional effectiveness
- Reduce inventory inefficiencies
- Align staffing with demand
- Optimize the menu
- Identify products that need attention
- Support regular, data-driven performance monitoring

> **Bottom line:** Use sales data continuously, not as a one-time analysis.

# 🗄️ 03 · SQL Analysis — Pizza Sales

> SQL queries that turn **48,620 raw order lines** into the KPIs, trends and rankings a pizza business needs to make decisions.

![SQL Server](https://img.shields.io/badge/SQL-T--SQL-blue)
![Database](https://img.shields.io/badge/Database-SQL%20Server-red)
![Queries](https://img.shields.io/badge/Queries-17-green)
![Year](https://img.shields.io/badge/Data-2015-orange)

---

## 📑 Table of Contents

1. [Objective](#-objective)
2. [Folder Contents](#-folder-contents)
3. [Dataset](#-dataset)
4. [Setup](#-setup)
5. [Queries Covered](#-queries-covered)
6. [Key Results](#-key-results)
7. [Business Insights](#-business-insights)
8. [SQL Skills Demonstrated](#-sql-skills-demonstrated)
9. [Notes & Compatibility](#-notes--compatibility)
10. [Acknowledgements](#-acknowledgements)

---

## 🎯 Objective

Use SQL to answer the core business questions for the pizza store:

- 💰 How much revenue did we make, and what is the average order value?
- ⏰ Which hours and weeks drive the most business?
- 🍽️ Which categories and sizes contribute the most to sales?
- 🏆 Which pizzas are best sellers, and which are underperforming?

---

## 📁 Folder Contents

| File | Description |
|------|-------------|
| `README.md` | Documentation for the SQL analysis (this file) |
| `pizza_sales_queries.sql` | All queries, organised by section (A to L), with table setup |
| `PIZZA_SALES_SQL_QUERIES.docx` | Original query document |

---

## 📊 Dataset

| Item | Details |
|------|---------|
| **Table** | `pizza_sales` |
| **Rows** | 48,620 (one row per pizza line item) |
| **Columns** | 12 |
| **Period** | 01 Jan 2015 to 31 Dec 2015 |
| **Orders** | 21,350 |
| **Pizza types** | 32 |

Column definitions are in the project's **Data Dictionary**.

---

## ⚙️ Setup

**1. Create the table**

```sql
CREATE TABLE pizza_sales (
    pizza_id          INT            NOT NULL PRIMARY KEY,
    order_id          INT            NOT NULL,
    pizza_name_id     VARCHAR(50)    NOT NULL,
    quantity          INT            NOT NULL,
    order_date        DATE           NOT NULL,
    order_time        TIME(0)        NOT NULL,
    unit_price        DECIMAL(10,2)  NOT NULL,
    total_price       DECIMAL(10,2)  NOT NULL,
    pizza_size        VARCHAR(5)     NOT NULL,
    pizza_category    VARCHAR(20)    NOT NULL,
    pizza_ingredients VARCHAR(400)   NOT NULL,
    pizza_name        VARCHAR(100)   NOT NULL
);
```

**2. Import `pizza_sales.csv`** (SSMS: *Tasks → Import Flat File*, or `BULK INSERT`).

**3. Fix the date format.** The CSV stores dates as `DD-MM-YYYY`, so run this before loading or querying:

```sql
SET DATEFORMAT dmy;
```

**4. Run** `pizza_sales_queries.sql` section by section.

---

## 🔍 Queries Covered

| Section | Analysis | Techniques |
|---------|----------|------------|
| **A** | 📈 KPIs: Total Revenue, Average Order Value, Total Pizzas Sold, Total Orders, Average Pizzas per Order | `SUM`, `COUNT(DISTINCT)`, `CAST` |
| **B** | ⏰ Hourly trend of pizzas sold | `DATEPART(HOUR)`, `GROUP BY` |
| **C** | 📅 Weekly trend of orders | `DATEPART(ISO_WEEK)`, `YEAR` |
| **D** | 🍽️ % of sales by pizza category | Subquery, percentage calculation |
| **E** | 📏 % of sales by pizza size | Subquery, percentage calculation |
| **F** | 🧮 Pizzas sold by category (February view) | `WHERE`, `MONTH()` |
| **G / H** | 💵 Top 5 / Bottom 5 pizzas by revenue | `TOP`, `ORDER BY` |
| **I / J** | 📦 Top 5 / Bottom 5 pizzas by quantity | `TOP`, `ORDER BY` |
| **K / L** | 🧾 Top 5 / Bottom 5 pizzas by total orders | `TOP`, `COUNT(DISTINCT)` |

### Example query

```sql
-- % of Sales by Pizza Category
SELECT pizza_category,
       CAST(SUM(total_price) AS DECIMAL(10,2)) AS Total_Revenue,
       CAST(SUM(total_price) * 100 /
            (SELECT SUM(total_price) FROM pizza_sales) AS DECIMAL(10,2)) AS Pct_of_Sales
FROM pizza_sales
GROUP BY pizza_category
ORDER BY Pct_of_Sales DESC;
```

---

## 📌 Key Results

### 💡 KPIs

| KPI | Value |
|-----|-------|
| 💰 Total Revenue | **817,860.05** |
| 🧾 Total Orders | **21,350** |
| 🍕 Total Pizzas Sold | **49,574** |
| 🛒 Average Order Value | **38.31** |
| 📦 Average Pizzas per Order | **2.32** |

### 🍽️ Sales by Category

| Category | Revenue | % of Sales |
|----------|---------|-----------|
| Classic | 220,053.10 | 26.91% |
| Supreme | 208,197.00 | 25.46% |
| Chicken | 195,919.50 | 23.96% |
| Veggie | 193,690.45 | 23.68% |

### 📏 Sales by Size

| Size | Revenue | % of Sales |
|------|---------|-----------|
| L | 375,318.70 | 45.89% |
| M | 249,382.25 | 30.49% |
| S | 178,076.50 | 21.77% |
| XL | 14,076.00 | 1.72% |
| XXL | 1,006.60 | 0.12% |

### 🏆 Top 5 and Bottom 5 Pizzas

| Rank | Top by Revenue | Top by Quantity | Top by Orders |
|------|----------------|-----------------|---------------|
| 1 | The Thai Chicken Pizza (43,434.25) | The Classic Deluxe Pizza (2,453) | The Classic Deluxe Pizza (2,329) |
| 2 | The Barbecue Chicken Pizza (42,768.00) | The Barbecue Chicken Pizza (2,432) | The Hawaiian Pizza (2,280) |
| 3 | The California Chicken Pizza (41,409.50) | The Hawaiian Pizza (2,422) | The Pepperoni Pizza (2,278) |
| 4 | The Classic Deluxe Pizza (38,180.50) | The Pepperoni Pizza (2,418) | The Barbecue Chicken Pizza (2,273) |
| 5 | The Spicy Italian Pizza (34,831.25) | The Thai Chicken Pizza (2,371) | The Thai Chicken Pizza (2,225) |

| Rank | Bottom by Revenue | Bottom by Quantity | Bottom by Orders |
|------|-------------------|--------------------|------------------|
| 1 | The Brie Carre Pizza (11,588.50) | The Brie Carre Pizza (490) | The Brie Carre Pizza (480) |
| 2 | The Green Garden Pizza (13,955.75) | The Mediterranean Pizza (934) | The Mediterranean Pizza (912) |
| 3 | The Spinach Supreme Pizza (15,277.75) | The Calabrese Pizza (937) | The Spinach Supreme Pizza (918) |
| 4 | The Mediterranean Pizza (15,360.50) | The Spinach Supreme Pizza (950) | The Calabrese Pizza (918) |
| 5 | The Spinach Pesto Pizza (15,596.00) | The Soppressata Pizza (961) | The Chicken Pesto Pizza (938) |

### ⏰ Busiest Hours (pizzas sold)

| Rank | Hour | Pizzas Sold |
|------|------|-------------|
| 1 | 12:00 to 12:59 | 6,776 |
| 2 | 13:00 to 13:59 | 6,413 |
| 3 | 18:00 to 18:59 | 5,417 |
| 4 | 17:00 to 17:59 | 5,211 |

---

## 🧠 Business Insights

- ⏰ **Two clear rush periods:** lunch (12 PM to 2 PM) and evening (5 PM to 7 PM). Staffing and prep should be planned around these windows.
- 📏 **Large pizzas drive the business:** size L alone brings in about 46% of revenue, while XL and XXL together contribute under 2%. These sizes are candidates for review.
- 🍗 **Chicken pizzas lead on revenue per pizza:** the top three revenue earners are all chicken pizzas, even though the Chicken category ranks third by share of sales.
- 🍽️ **Categories are well balanced:** all four sit between 23% and 27% of revenue, so no single category carries the menu.
- 📉 **Brie Carre is the weakest performer by a wide margin:** it sells roughly half as many as the next-lowest pizza on quantity, revenue and orders.
- 🛒 **Average order is about 2.3 pizzas worth 38.31:** upselling a side or drink to each order is a straightforward way to lift revenue.
- 📅 **Weekly orders peak in week 48 (491 orders).** The last week of the year is only partial (data ends 31 Dec), so its low count should not be read as a real drop.

---

## 🧰 SQL Skills Demonstrated

- ✅ Aggregations: `SUM`, `COUNT`, `COUNT(DISTINCT)`
- ✅ Grouping and sorting: `GROUP BY`, `ORDER BY`, `TOP`
- ✅ Date and time functions: `DATEPART`, `YEAR`, `MONTH`
- ✅ Subqueries for percentage-of-total calculations
- ✅ Data type casting for clean, rounded output
- ✅ Filtering with `WHERE` to slice by category, size or month

---

## 📝 Notes & Compatibility

- The queries are written in **T-SQL (SQL Server)**.
- **Query F** is filtered to **February**. Remove the `WHERE` clause for the full-year view, or change the month number.
- `TOP 5` returns exactly five rows even if there are ties.
- To filter any query by category or size, add a `WHERE` clause, for example `WHERE pizza_category = 'Classic'`.

**Using another database?**

| SQL Server | MySQL | PostgreSQL |
|------------|-------|------------|
| `TOP 5` | `LIMIT 5` | `LIMIT 5` |
| `DATEPART(HOUR, order_time)` | `HOUR(order_time)` | `EXTRACT(HOUR FROM order_time)` |
| `DATEPART(ISO_WEEK, order_date)` | `WEEK(order_date, 3)` | `EXTRACT(WEEK FROM order_date)` |

---

## 🙏 Acknowledgements

The query set follows a tutorial document from the **Data Tutorials** YouTube channel. Results in this README were checked against the dataset in this project.

---

⬅️ [Back to project home](../README.md)

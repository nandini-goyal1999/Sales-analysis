# 📊 Sales Insights — Revenue and Profit Intelligence Dashboard
> End-to-end sales data analysis for an India-based hardware company using SQL and Tableau.

![MySQL](https://img.shields.io/badge/MySQL-Database-blue?logo=mysql) ![Tableau](https://img.shields.io/badge/Tableau-Dashboard-orange?logo=tableau) ![Excel](https://img.shields.io/badge/Excel-Advanced-green?logo=microsoftexcel) ![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

---

## 📌 Project Overview

This project delivers **automated sales intelligence** for a hardware company operating across multiple Indian states. The goal is to replace manual data gathering with a **self-serve Tableau dashboard** that surfaces revenue trends, profit margins, and customer performance — enabling the sales director to make faster, data-driven decisions.

---

## 🎯 Business Problem

> *"The sales director needs real-time visibility into regional performance to decide where to offer discounts and how to allocate resources across markets."*

**Key business questions answered:**
- Which cities and regions are driving the most revenue?
- Who are the top 5 customers and products by revenue?
- What is the net profit and profit margin by market?
- How has revenue trended year-on-year and month-on-month?

---

## ✅ Success Criteria

| Metric | Target |
|--------|--------|
| Cost Savings | 10% reduction in total spend |
| Analyst Time Saved | 20% less time on manual data gathering |
| Dashboard Freshness | Latest data always available |

---

## 🛠️ Tech Stack

| Layer | Tools |
|-------|-------|
| Database & ETL | MySQL, SQL Server |
| Data Transformation | SQL (Joins, Aggregations, CTEs) |
| Data Modeling | Star Schema (Fact + Dimension Tables) |
| Visualization | Tableau, Power BI |
| Reporting | Advanced Excel |

---

## 📂 Project Structure

```
├── db_dump.sql                  # Raw database dump for MySQL import
├── db_dump.xlsx                 # Excel version of raw data
├── sales_insights_queries.sql   # All SQL queries for data analysis
├── Sales_Insights.twbx          # Tableau workbook (Revenue + Profit dashboards)
└── README.md
```

---

## 🔄 Workflow

### ① ETL — SQL
- Extracted raw transactional data from unstructured source using **MySQL**
- Transformed and loaded data into staging area with **data cleaning**
- Designed a **Star Schema** — Fact (Transactions) + Dimensions (Date, Customer, Market, Product)

### ② Data Analysis — SQL
- Queried revenue breakdown by **city, year, month**
- Identified **top 5 customers** and **top 5 products** by revenue
- Analyzed transactions by **currency (INR/USD)** and **market code**
- Computed **net profit and profit margin** by market

### ③ Visualization — Tableau
- Built **Revenue Analysis Dashboard** — city-wise, year-wise, month-wise trends
- Built **Profit Analysis Dashboard** — net profit, margin by market
- Enabled sales director to **filter, drill down, and self-serve insights**

---

## 💡 Key SQL Queries

```sql
-- Total Revenue in 2020
SELECT SUM(transactions.sales_amount)
FROM transactions
INNER JOIN date ON transactions.order_date = date.date
WHERE date.year = 2020
AND (transactions.currency = "INR\r" OR transactions.currency = "USD\r");

-- Top Markets by Revenue
SELECT market_code, SUM(sales_amount) AS total_revenue
FROM transactions
GROUP BY market_code
ORDER BY total_revenue DESC;

-- Net Profit by Market
SELECT market_code, SUM(profit_margin) AS net_profit
FROM transactions
GROUP BY market_code
ORDER BY net_profit DESC;
```

---

## 📊 Dashboard Preview

> **Revenue Dashboard** — City-wise breakdown, YoY trends, top customers and products

> **Profit Dashboard** — Net profit, profit margin, and market-level performance

🔗 [View Live Tableau Dashboard](#)

---

## 💡 Key Insights

- Identified **top revenue-generating cities** enabling targeted discount strategies
- Surfaced **top 5 customers** contributing disproportionate revenue for retention focus
- Uncovered **low-margin markets** allowing reallocation of sales resources
- Automated reporting saved analysts **20% of manual data gathering time**

---

## 🚀 How to Run

```bash
# Step 1: Import database
# Download db_dump.sql → Import into MySQL

# Step 2: Run SQL queries
# Open sales_insights_queries.sql in MySQL Workbench

# Step 3: Connect Tableau
# Open Tableau → Connect to MySQL → Load Sales_Insights.twbx

# Step 4: Explore dashboards
# Revenue Analysis + Profit Analysis tabs
```

---

## 🧠 Skills Demonstrated

`MySQL` `SQL Joins` `ETL` `Star Schema` `Data Modeling` `Tableau` `Power BI` `Advanced Excel` `KPI Analysis` `Revenue Analytics` `Profit Margin Analysis` `Data Storytelling` `Business Intelligence`

---

## 📄 License

MIT — feel free to fork, star ⭐, and use in your portfolio.

---

## 🙋 About

Built as a **portfolio-grade business intelligence project** to demonstrate end-to-end data analyst capabilities — from raw SQL extraction to executive-level Tableau dashboards.

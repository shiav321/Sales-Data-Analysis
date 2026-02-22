# ðŸ“Š Sales Data Analysis using SQL & MySQL

<div align="center">

![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

**A complete SQL-based data analysis project on sales database â€” uncovering product performance, revenue trends, and customer insights using MySQL.**

</div>

---

## ðŸ“Œ Problem Statement

Businesses generate massive sales data daily but struggle to extract meaningful insights from it. This project demonstrates how SQL can be used to analyze a sales database and answer critical business questions â€” helping companies make smarter, data-driven decisions.

---

## ðŸŽ¯ Key Business Questions Answered

- ðŸ† Which are the **top-selling products** by revenue?
- ðŸ“… What are the **monthly and yearly sales trends**?
- ðŸ‘¥ Who are the **highest-value customers**?
- ðŸŒ Which **regions/areas** generate the most revenue?
- ðŸ“‰ Which products are **underperforming**?
- ðŸ’° What is the **average order value** per category?

---

## ðŸ—„ï¸ Database Schema

```
sales_database
â”‚
â”œâ”€â”€ ðŸ“‹ customers        (customer_id, name, region, email)
â”œâ”€â”€ ðŸ“¦ products         (product_id, name, category, price)
â”œâ”€â”€ ðŸ›’ orders           (order_id, customer_id, order_date, total_amount)
â””â”€â”€ ðŸ“ order_items      (item_id, order_id, product_id, quantity, unit_price)
```

---

## ðŸ” Key SQL Queries

### Top 5 Products by Revenue
```sql
SELECT 
    p.name AS product_name,
    SUM(oi.quantity * oi.unit_price) AS total_revenue
FROM order_items oi
JOIN products p ON oi.product_id = p.product_id
GROUP BY p.name
ORDER BY total_revenue DESC
LIMIT 5;
```

### Monthly Sales Trend
```sql
SELECT 
    DATE_FORMAT(order_date, '%Y-%m') AS month,
    COUNT(order_id) AS total_orders,
    SUM(total_amount) AS monthly_revenue
FROM orders
GROUP BY month
ORDER BY month;
```

### Customer Lifetime Value
```sql
SELECT 
    c.name AS customer_name,
    COUNT(o.order_id) AS total_orders,
    SUM(o.total_amount) AS lifetime_value
FROM customers c
JOIN orders o ON c.customer_id = o.customer_id
GROUP BY c.name
ORDER BY lifetime_value DESC;
```

---

## ðŸ“‚ Project Structure

```
sales-data-analysis/
â”‚
â”œâ”€â”€ ðŸ“„ database_schema.sql      # Table creation scripts
â”œâ”€â”€ ðŸ“„ sample_data.sql          # Sample insert statements
â”œâ”€â”€ ðŸ“„ analysis_queries.sql     # All analysis queries
â””â”€â”€ ðŸ“– README.md                # Project documentation
```

---

## ðŸš€ How to Run

```bash
# Step 1: Open MySQL Workbench or any MySQL-compatible tool

# Step 2: Create the database
CREATE DATABASE sales_db;
USE sales_db;

# Step 3: Run schema to create tables
source database_schema.sql;

# Step 4: Insert sample data
source sample_data.sql;

# Step 5: Run analysis queries
source analysis_queries.sql;
```

---

## ðŸ“ˆ Sample Insights Found

| Insight | Finding |
|---------|---------|
| ðŸ† Best Selling Product | Electronics category leads revenue |
| ðŸ“… Peak Sales Month | November-December (festive season) |
| ðŸ‘¥ Avg Order Value | â‚¹2,450 per transaction |
| ðŸŒ Top Region | South India â€” highest volume |

---

## ðŸ› ï¸ Tech Stack

| Tool | Purpose |
|------|---------|
| MySQL | Database & query engine |
| MySQL Workbench | Query development & visualization |
| SQL | Data analysis & reporting |
| Excel | Results visualization |

---

## ðŸŒ Real-World Applications

- Retail businesses tracking product performance
- E-commerce platforms analyzing customer behavior  
- Supply chain optimization using demand patterns
- Sales team performance dashboards

---

## ðŸ‘¨â€ðŸ’» About the Developer

**Shiva Keshava** â€” B.Tech AI & Data Science Graduate

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat&logo=linkedin)](https://linkedin.com/in/shiva-keshava-b71355364)
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-FF6B6B?style=flat&logo=google-chrome)](https://shivaprofilewebsite.lovable.app/)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=flat&logo=github)](https://github.com/shiav321)

---

<div align="center">
â­ If this project helped you, please give it a star!
</div>

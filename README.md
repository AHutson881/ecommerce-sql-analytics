# E-Commerce Analytics SQL + Python Project

This project simulates a complete business analysis workflow for a fictional e-commerce company. Using Python and MySQL, I generated and explored a normalized relational dataset of customers, orders, products, and returns — structured to reflect real-world operations and user behavior. The project includes database creation, synthetic data generation, business insights through SQL, and structured data exports in both CSV and Excel formats.

---

## Business Goal

**How can this e-commerce company increase revenue while reducing product returns and improving customer retention?**

This project frames all analysis and reporting around answering this core question using SQL-driven insights and operational patterns.

---

## Database Schema

- **customers** — customer_id, first_name, last_name, email, signup_date
- **products** — product_id, product_name, category, price
- **orders** — order_id, customer_id, order_date, total_amount
- **order_items** — order_item_id, order_id, product_id, quantity, item_price
- **returns** — return_id, order_item_id, return_date, reason

---

## Key Analytical Questions

- What product categories generate the most revenue?
- Which customers have the highest lifetime value?
- What are the most returned products and why?
- How do return rates differ by product or category?
- What is the monthly revenue trend?

---

## Folder Structure

```
ecommerce_sql_project/
│
├── generate_data.py          # Python: generates & populates all base tables
├── export_data.py            # Python: exports tables to CSV
├── export_to_excel.py        # Python: exports all base tables to Excel
│
├── exported_data/
│   ├── ecommerce_database.xlsx     # All base tables in a single .xlsx file
│   ├── original_tables/            # Raw base tables as .csv
│   └── derived_tables/             # SQL query results / summaries as .csv
│
├── SQL_Scripts/
│   ├── ecommerceDB_setup.sql           # CREATE TABLE statements
│   ├── ecommerce_data_exploration.sql  # All analysis queries
│   └── derived_tables.sql              # CREATE TABLE AS queries
│
└── README.md                   # This file
```

---

## Skills Highlighted

- Relational database schema design (MySQL)
- Synthetic data generation with Python and Faker
- SQL queries: joins, aggregations, groupings, subqueries
- Analysis of customer behavior and product performance
- Data export automation (CSV and Excel)
- Clean project documentation and structure

---

## 📥 To Reproduce

1. Set up MySQL and run `ecommerceDB_setup.sql`
2. Run `generate_data.py` to populate with data
3. Run `derived_tables.sql` to create analytical tables
4. Run `export_data.py` and/or `export_to_excel.py` for exports
5. Use SQL scripts in `SQL_Scripts/` to explore insights

---
# Let me know your thoughts or any questions!

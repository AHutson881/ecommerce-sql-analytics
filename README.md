# E-Commerce Analytics SQL + Python  + Power BI Project

This project simulates a complete business analysis workflow for a fictional e-commerce company. Using Python and MySQL, I generated and explored a normalized relational dataset of customers, orders, products, and returns that was structured to reflect real-world operations and user behavior using synthetic data. The project includes database creation, synthetic data generation, business insights through SQL, and structured data exports in both CSV and Excel formats. A PowerBI aspect to this will also be available shortly on my GitPages portfolio here -> https://ahutson881.github.io/allisonh-portfolio/#

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

## To Reproduce

1. Set up MySQL and run `ecommerceDB_setup.sql`
2. Run `generate_data.py` to populate with data
3. Run `derived_tables.sql` to create analytical tables
4. Run `export_data.py` and/or `export_to_excel.py` for exports
5. Use SQL scripts in `SQL_Scripts/` to explore insights

---
## PowerBI Report Creation

# E-Commerce SQL Analytics Project

Using the simulated data from before to create an interactive dashboard using Power BI. (Shown on my portfolio pages statically because I do not have an actual PowerBI account currently.)

# Objective

**Analyze customer behavior, purchase trends, and return patterns** to identify high-value customers and product performance. Key metrics include:

- Total Revenue
- Return Rate
- Average Order Value
- Customer Lifetime Value (CLV)
- Revenue by Category & Customer Tier

---

## ⚙️ Tools Used

- **MySQL**: Database schema design and querying  
- **Python (pandas, MySQL connector)**: Synthetic data generation and export  
- **Power BI Desktop**: Interactive dashboard creation  
- **Git & GitHub**: Version control and portfolio publication  

---

## Data Generation & Adjustments

- **Synthetic data** generated via Python to simulate:
  - Customers, orders, products, order items, and returns  
- **Fixes Made:**
  - Added realistic `signup_date` and `return_date` using `datetime` ranges  
  - Ensured `Customer Lifetime Value` is calculated based on actual `total_amount` from `orders`  
  - Product names were updated to be more natural-sounding  
  - Derived tables were regenerated using corrected date values  

### Derived Tables (Examples)

- `total_revenue_by_category`
- `customer_lifetime_value`
- `monthly_revenue_trend`
- `top_returned_products`
- `return_rate_by_product`
- `return_rate_by_category`
- `top_customers_by_spend`

---

## Power BI Dashboard Design

### Dashboard Pages

#### 1. **Main Dashboard**

Includes:

- KPI Cards for:
  - Total Revenue
  - Return Rate (%)
  - Average Order Value
- Trend Visuals:
  - Monthly Revenue
  - Monthly Return Count
- Segmentations:
  - CLV by Customer Name
  - Revenue and Customer Count by Revenue Tier
  - Revenue by Product Category

#### 2. **KPI & Trend Details**

Drilldown into:

- Revenue trends
- Product category breakdowns
- Customer purchase behavior

### Custom Measures Used (DAX):

DAX
Customer Lifetime Value = 
CALCULATE(
    SUM(orders[total_amount]),
    FILTER(orders, orders[customer_id] = MAX(customers[customer_id]))
)

Total Revenue = 
SUMX(order_items, order_items[quantity] * order_items[item_price])

Return Rate (%) = 
DIVIDE(COUNT(returns[return_id]), COUNT(order_items[order_item_id]))

Average Order Value = 
AVERAGEX(orders, orders[total_amount])
Revenue Tier =
SWITCH(
    TRUE(),
    [Customer Lifetime Value] >= 1000, "High Value",
    [Customer Lifetime Value] >= 500, "Mid Value",
    [Customer Lifetime Value] >= 0, "Low Value",
    "Unknown"
)'''

## How to Reproduce
Clone this repo

Run generate_data.py to create and populate your MySQL database

Use export_data.py or db_export_full.py to export data to CSV or Excel

Open ecommerce_database.xlsx in Power BI Desktop

Load tables, clean data types, define relationships, and build visuals

# Sample Insights
40% of customers fall into the High Value Tier

Electronics generates the highest category revenue

CLV distributions are skewed toward 2–3 power users

Return rate hovers near 39%, driven mostly by "Wrong item delivered"

# Author
Allison Hutson
Customer Insights & Product Research Strategist

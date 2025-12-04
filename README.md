📦 Zepto Product Data Analysis — SQL Case Study

A real-world SQL project analyzing retail product, pricing, and inventory data to generate actionable business insights.

🚀 Project Overview

This SQL project simulates a real analytics workflow for Zepto-style product data. It covers schema design, data cleaning, exploration, and business insight generation—highlighting practical SQL expertise and analytical thinking.

⭐ My Key Contributions (Impact-Driven)
1️⃣ Designed a complete SQL data model for retail analytics

Created a normalized schema covering SKU metadata, pricing, quantity, and stock states.

Ensured dataset readiness for exploration, BI reporting, and downstream analysis.

2️⃣ Cleaned & validated 5,000+ product records for accurate analysis

Removed 100% invalid pricing entries (MRP = 0).

Converted paise → rupees for 2+ pricing fields using bulk updates.

Identified and flagged missing values across name, category, and pricing columns.

Ensured internal consistency between discount %, MRP, and selling price.

3️⃣ Built 20+ SQL queries for data exploration & quality checks

Including:

Null detection

Duplicate checks

Category distribution

Out-of-stock trends

High-MRP and high-discount product detection

This established a clear data sanity profile before deeper analysis.

4️⃣ Performed detailed business analysis across pricing, inventory & revenue

Generated insights using SQL aggregations such as:

Top 10 highest-discounted products

Revenue estimation per category

Value per gram for identifying best-value SKUs

Inventory weight analysis to assess category movement

High-MRP items that frequently stock out to inform demand planning

5️⃣ Uncovered 6+ actionable insights for business decision-making

Examples include:

Certain categories consistently contribute highest revenue share.

Several high-MRP items were out of stock, signaling high demand.

Weight-based value analysis highlighted price inefficiencies.

Discount patterns showed which categories attract most purchases.

6️⃣ Built modular, production-friendly SQL scripts

Organized the entire project into reusable modules:

zepto-sql-analysis/
│── zepto_schema.sql
│── data_cleaning.sql
│── exploration_queries.sql
│── analysis_queries.sql
└── README.md


This structure supports real-world collaboration, reusability, and scalability.

📈 Example Analysis Queries
🔹 Revenue by Category
SELECT category,
       SUM(discountedSellingPrice * availableQuantity) AS total_revenue
FROM zepto
GROUP BY category;

🔹 Highest Discount Products
SELECT name, mrp, discountPercent
FROM zepto
ORDER BY discountPercent DESC
LIMIT 10;

🔹 Price per Gram
SELECT name, weightInGms, discountedSellingPrice,
       ROUND(discountedSellingPrice / weightInGms, 2) AS price_per_gram
FROM zepto
WHERE weightInGms >= 100;

💡 What This Project Demonstrates
✔ Strong SQL fundamentals (DDL + DML + analytical queries)
✔ Real-world data cleaning and validation
✔ Business intelligence mindset
✔ Ability to convert raw data into clear insights
✔ Portfolio-ready project execution & documentation
🛠️ Tech Stack

PostgreSQL

SQL (joins, aggregations, CTEs, cleaning)

Git/GitHub

🔮 Future Enhancements

Build an interactive dashboard (Power BI / Tableau)

Predict out-of-stock products using ML

Automate processes using Python pipelines

👨‍💻 Author

Danish Ansari
📧 danishansari9336@gmail.com

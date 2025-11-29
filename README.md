📦 Zepto Product Data Analysis (SQL Project)
A structured SQL project analyzing product data from Zepto, focusing on data exploration, cleaning, and business insights generation.
Designed as a real-world, resume-ready project showcasing SQL skills.

🚀 Project Highlights

Created a robust SQL schema for retail product data

Performed data cleaning (null checks, removing invalid pricing, unit conversions)

Explored dataset through descriptive SQL queries

Conducted insightful business analysis:

Revenue estimation

Discount optimization

Stock availability trends

Category-based insights

Value-for-money comparisons

🗂️ Dataset Structure

The table zepto includes:

Column	Description
sku_id	Unique SKU identifier
category	Product category
name	Product name
mrp	Maximum Retail Price
discountPercent	Discount applied (%)
discountedSellingPrice	Selling price after discount
availableQuantity	Units available
weightInGms	Product weight
outOfStock	Boolean stock status
quantity	Purchased quantity
🧪 Data Exploration

✔ Count rows
✔ Check unique categories
✔ Identify duplicates
✔ Find nulls
✔ In-stock vs out-of-stock analysis

SELECT outOfStock, COUNT(*) FROM zepto GROUP BY outOfStock;

🧼 Data Cleaning Steps
🔹 1. Remove invalid pricing
DELETE FROM zepto WHERE mrp = 0;

🔹 2. Convert paise → rupees
UPDATE zepto
SET mrp = mrp / 100.0,
    discountedSellingPrice = discountedSellingPrice / 100.0;

🔹 3. Handle nulls (detection)
SELECT * FROM zepto
WHERE name IS NULL OR category IS NULL OR mrp IS NULL;

📊 Key Analysis Queries
⭐ Top 10 Products with Highest Discounts
SELECT name, mrp, discountPercent
FROM zepto
ORDER BY discountPercent DESC
LIMIT 10;

⭐ High-MRP Items That Are Out of Stock
SELECT name, mrp
FROM zepto
WHERE outOfStock = TRUE AND mrp > 300;

⭐ Estimated Revenue Per Category
SELECT category,
SUM(discountedSellingPrice * availableQuantity) AS total_revenue
FROM zepto
GROUP BY category;

⭐ Products with High MRP & Low Discounts
SELECT name, mrp, discountPercent
FROM zepto
WHERE mrp > 500 AND discountPercent < 10;

⭐ Weight-Based Value Analysis (Price per Gram)
SELECT name, weightInGms, discountedSellingPrice,
ROUND(discountedSellingPrice / weightInGms, 2) AS price_per_gram
FROM zepto
WHERE weightInGms >= 100;

⭐ Category-Based Inventory Weight
SELECT category,
SUM(weightInGms * availableQuantity) AS total_weight
FROM zepto
GROUP BY category;

📈 Insights Generated

Identified best-value products based on discount %

Found high MRP items frequently going out of stock

Computed total revenue contributions across categories

Recognized categories offering the highest average discounts

Classified products into Low / Medium / Bulk weight buckets

🛠️ Tech Stack

PostgreSQL

SQL (DDL, DML, Data Cleaning, Aggregations)

Query Optimization

Exploratory Data Analysis (EDA)

📁 Project Structure
📦 zepto-sql-analysis
│
├── zepto_schema.sql
├── data_cleaning.sql
├── exploration_queries.sql
├── analysis_queries.sql
└── README.md

🎯 What This Project Demonstrates

SQL mastery (DDL, DML, joins, aggregations, conditions)

Real-world data cleaning techniques

Business-focused analysis

Ability to derive insights from raw datasets

Portfolio-quality documentation

💡 Future Enhancements

Create dashboards in Power BI / Excel / Tableau

Predict out-of-stock products using ML

Build a Python pipeline for automation

👨‍💻 Author

Danish Ansari
📧 danishansari9336@gmail.com

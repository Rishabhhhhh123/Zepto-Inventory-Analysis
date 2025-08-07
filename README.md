# 🛒 Zepto E-commerce SQL Data Analyst Portfolio Project

This is a professional, real-world SQL Data Analytics project built using an inventory dataset scraped from **Zepto**, one of India’s fastest-growing quick-commerce startups. The project simulates how data analysts handle raw e-commerce data — from exploration and cleaning to advanced business analysis — to derive actionable insights.

---

## 📌 Project Highlights

✔️ Real-world e-commerce inventory use case  
✔️ 20+ SQL queries for revenue, pricing, and inventory analytics  
✔️ Industry-grade data cleaning, EDA, and performance optimization  
✔️ Built for job interviews, portfolios, and real analyst workflow simulation  

---

## 🧠 Project Objectives

This project simulates the end-to-end process followed by data analysts in real-world business environments:

- Design and create the inventory database schema  
- Load and clean a large inventory dataset  
- Perform structured EDA (Exploratory Data Analysis)  
- Derive actionable business insights using advanced SQL queries  
- Present metrics such as turnover ratio, stock-outs, and profitability  

---

## 📁 Dataset Overview

The dataset used for this project is sourced from Kaggle: **[Zepto Inventory Dataset](https://www.kaggle.com/datasets)**  
It closely replicates a real-world e-commerce inventory system, scraped from Zepto's official product listings.

Each row represents a unique **SKU (Stock Keeping Unit)** — a granular view of individual products, including variations in weight, packaging, or discount schemes.

---

## 🧾 Column Descriptions

| Column Name             | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| `sku_id`                | Unique identifier for each SKU (Synthetic Primary Key)                     |
| `name`                  | Product name as listed on the Zepto app                                    |
| `category`              | Product category (e.g., Fruits, Snacks, Beverages)                         |
| `mrp`                   | Maximum Retail Price (converted to ₹ from paise)                           |
| `discountPercent`       | Percentage of discount applied on MRP                                      |
| `discountedSellingPrice`| Final price after applying discount (in ₹)                                 |
| `availableQuantity`     | Inventory count indicating stock availability                              |
| `weightInGms`           | Net product weight in grams                                                |
| `outOfStock`            | Boolean flag (TRUE/FALSE) indicating stock status                          |
| `quantity`              | Quantity per unit/package (integers or grams for loose items)              |

---

## 🛠️ Tools & Technologies

- PostgreSQL (SQL)  
- pgAdmin 4  
- CSV (UTF-8 Format)  
- Git & GitHub  

---

## 🔧 Step-by-Step Project Workflow

### 1️⃣ Database Schema Creation

```sql
CREATE TABLE zepto (
  sku_id SERIAL PRIMARY KEY,
  category VARCHAR(120),
  name VARCHAR(150) NOT NULL,
  mrp NUMERIC(8,2),
  discountPercent NUMERIC(5,2),
  availableQuantity INTEGER,
  discountedSellingPrice NUMERIC(8,2),
  weightInGms INTEGER,
  outOfStock BOOLEAN,
  quantity INTEGER
);
2️⃣ Data Import
Used pgAdmin 4’s import feature with UTF-8 encoding

Alternate method using SQL:

sql
Copy
Edit
\copy zepto(category,name,mrp,discountPercent,availableQuantity,
            discountedSellingPrice,weightInGms,outOfStock,quantity)
FROM 'data/zepto_v2.csv'
WITH (FORMAT csv, HEADER true, DELIMITER ',', QUOTE '"', ENCODING 'UTF8');

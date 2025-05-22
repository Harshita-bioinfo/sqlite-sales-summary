# 📊 Retail Sales Analytics using SQLite and Python

## 📦 Overview

This project implements a lightweight, SQL-based retail analytics system using a relational database (`sales_data.db`) and visualizes key sales metrics using Python libraries. It simulates real-world retail data, including product sales, discounts, regional patterns, and customer behavior.

The system supports analytics such as:

- 🛒 Revenue trends by category and date
- 📈 Product-wise profitability and popularity
- 🌍 Region-based buying behavior
- 🎯 Top customers and anomalies in sales
- 🔄 Repeat purchases and customer loyalty

The goal is to build business intelligence dashboards using simple SQL queries, pandas data handling, and seaborn/matplotlib visualizations.

---

## 📁 Repository Structure

| File / Folder                    | Description                                                                 |
|----------------------------------|-----------------------------------------------------------------------------|
| `Basic_Sales_Summary_SQLite.ipynb` | Jupyter Notebook containing the complete analysis and visualizations       |
| `SQL_queries_Output/`                | Folder containing images of the query outputs                          |
| `README.md`                      | Project documentation and usage instructions                                         |

---

## 🛠️ Tools & Technologies Used

| Tool           | Purpose                                |
|----------------|----------------------------------------|
| Python 3.x     | Core programming language              |
| SQLite         | Lightweight relational database        |
| sqlite3        | Python module to interact with SQLite  |
| pandas         | DataFrame management and SQL ingestion |
| seaborn        | Statistical data visualization         |
| matplotlib     | Chart rendering engine                 |

---

## 🗃️ Database Schema

### Database: `sales_data.db`

**Table: `sales`**

| Column           | Type     | Description                        |
|------------------|----------|------------------------------------|
| `sale_id`        | INTEGER  | Unique transaction ID (PK)         |
| `customer_id`    | INTEGER  | Unique customer ID                 |
| `customer_region`| TEXT     | Region of the customer             |
| `product_name`   | TEXT     | Product sold                       |
| `category`       | TEXT     | Product category                   |
| `quantity`       | INTEGER  | Units sold                         |
| `price_per_unit` | REAL     | Sale price per unit                |
| `discount`       | REAL     | Discount applied (%)               |
| `sale_date`      | TEXT     | Transaction date                   |
| `payment_method` | TEXT     | Mode of payment                    |

---

## 🔄 Step-by-Step Workflow

| Step | Description |
|------|-------------|
| 1️⃣ | Imported required libraries (`sqlite3`, `pandas`, `matplotlib`, `seaborn`) |
| 2️⃣ | Created and connected to SQLite database `sales_data.db` |
| 3️⃣ | Defined schema for `sales` table and inserted 30 dummy sales records |
| 4️⃣ | Wrote and executed 10 SQL queries for sales analysis |
| 5️⃣ | Converted query results into DataFrames using `pandas.read_sql_query()` |
| 6️⃣ | Visualized each analysis using seaborn/matplotlib (bar, line, heatmap, pie, scatter) |
| 7️⃣ | Highlighted key insights: revenue trends, top products, discounts, and customer behavior |

---

## 📊 SQL Queries & Visual Insights

| # | Query Purpose                                      | SQL Summary                                          | Visualization Type        |
|---|----------------------------------------------------|------------------------------------------------------|----------------------------|
| 1 | Total revenue by product **category**              | `GROUP BY category` with revenue calculation         | Horizontal bar chart       |
| 2 | Daily revenue trend                                | `GROUP BY sale_date` ordered chronologically         | Line chart                 |
| 3 | Top-selling products by quantity                   | `GROUP BY product_name` with `SUM(quantity)`         | Horizontal bar chart       |
| 4 | Average discount by category                       | `AVG(discount)` `GROUP BY category`                 | Horizontal bar chart       |
| 5 | Regional buying behavior by category               | `GROUP BY region, category`                          | Heatmap                    |
| 6 | Estimated profit per product (30% margin assumed)  | `SUM(quantity * price * 0.3 * (1 - discount))`       | Horizontal bar chart       |
| 7 | Category contribution to total revenue             | `WITH total ... % contribution using ROUND()`        | Pie chart                  |
| 8 | Anomalies in discount or zero revenue              | Filter rows with `discount > 10` or zero revenue     | Scatter plot               |
| 9 | Top customers by lifetime value                    | `GROUP BY customer_id` with total revenue calc       | Horizontal bar chart       |
| 10| Products with most repeat buyers                   | `COUNT(DISTINCT customer_id)` `GROUP BY product`     | Horizontal bar chart       |

---

## 📈 Key Business Insights

- 💸 **Electronics** and **Furniture** dominate revenue streams.
- 🧾 Some products show **frequent repeat purchases**, indicating loyalty.
- 🌍 **Region-wise analysis** reveals category preferences (e.g., more furniture sales in the East).
- 📉 Products with high **discounts** need monitoring for profitability.
- 📌 **Top 10 customers** account for a major portion of total revenue.

---

## 🚀 How to Run the Project

### 🖥️ Requirements

Install required Python packages (if not already installed):
```bash
pip install pandas matplotlib seaborn
````

### 🧪 Execution Steps

1. **Clone the repository**

   ```bash
   git clone https://github.com/Harshita-bioinfo/sqlite-sales-summary.git
   cd sqlite-sales-summary
   ```

2. **Launch the notebook**

   ```bash
   jupyter notebook Basic_Sales_Summary_SQLite.ipynb
   ```

3. **Run all cells to:**

   * Create and populate the SQLite database
   * Execute all SQL queries
   * Visualize each analytical insight

---



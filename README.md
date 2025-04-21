
<h1 align="center">📊 Sales-Management-System-DB – SQL Data Analysis & Relational DB Project</h1>

<p align="center">
  <img src="https://img.shields.io/badge/SQL-Server-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/Mockaroo-Fake%20Data-green?style=flat-square" />
  <img src="https://img.shields.io/badge/AI%20Assisted-Yes-purple?style=flat-square" />
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square" />
</p>

---

## 🔍 Overview

Sales-Management-System-DB is a fictional sales database project created to demonstrate SQL expertise, from **manual ERD design**, **schema creation**, and **dummy data generation**, to solving real-world business scenarios using **advanced SQL techniques**.

The project simulates a realistic environment where data is structured and queried as if it were a live business sales system — with departments, customers, orders, sales reps, and more.

---

## 📐 ERD & Database Design

The **Entity Relationship Diagram (ERD)** was manually designed to define relationships between all major entities.  
Key points:

- Normalized structure (up to 3NF)
- Strong entity relationships using **primary/foreign keys**
- Real-world integrity constraints and business logic

🖼️ *ERD file is included in this repo as `ERD_SmartSalesDB.png`.*

---

## 🧪 Data Generation

All data in this project is **fake** and used purely for learning purposes. It was generated using:

- ✅ [Mockaroo](https://mockaroo.com/) — for custom data schema matching the ERD
- ✅ **AI tools** — for generating product names, categories, and logic-based fields
- ✅ ✍️ Manual curation — to inject edge cases and natural-looking values

---

## 🧰 Tech Stack

| Tool / Language | Purpose |
|-----------------|---------|
| SQL Server       | Core database engine |
| SSMS             | Database management |
| dbdiagram.io / Draw.io | ERD design |
| Mockaroo         | Dummy data generation |
| Markdown         | Project documentation |

---

## 📁 Repository Structure















---

## 🎯 Key SQL Concepts Demonstrated

- ✅ Advanced `JOIN`s & filtering
- ✅ Subqueries (scalar, correlated)
- ✅ Aggregations & `GROUP BY`
- ✅ Window functions: `RANK`, `ROW_NUMBER`, `DENSE_RANK`
- ✅ Views, procedures, and indexing
- ✅ Triggers & data automation
- ✅ Creating read-only users and permission management

---

## ✨ Sample Query: Ranking Top 3 Sales Representatives

```sql
WITH Total_Sales_Rep AS (
  SELECT sr.Sales_rep_id, Full_name, SUM(total_amount) AS Total_Sales
  FROM Sales_rep sr
  JOIN Orders o ON sr.Sales_rep_id = o.Sales_rep_id
  GROUP BY sr.Sales_rep_id, Full_name
)
SELECT TOP 3 * 
FROM Total_Sales_Rep 
ORDER BY Total_Sales DESC;


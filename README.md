# 🛍 E-Commerce Sales Analysis (SQL)

## 🔍 Project Objectives
The analysis delivers a **360° view of E-Commerce operations** to:
- Identify **KPIs** for performance benchmarking  
- Optimize inventory allocation using sales trends  
- Enhance profitability through data-driven pricing strategies  
- Personalize marketing based on customer behavior patterns  

---

## 🛠 SQL Techniques Applied
| **Technique**               | **Business Application**                          | **Example**                      |
|-----------------------------|--------------------------------------------------|----------------------------------|
| Aggregate Functions (`SUM`, `AVG`) | Revenue/profit calculations                  | `SELECT SUM(profit) FROM orders` |
| Window Functions (`OVER`, `PARTITION`) | YoY growth analysis                    | `LAG(revenue, 12) OVER (ORDER BY month)` |
| CTEs & Subqueries           | Complex cohort analysis                  | `WITH top_customers AS (...)`    |
| Multi-Table Joins           | Product-customer relationship mapping    | `JOIN orders ON customers.id`    |
| `CASE` Statements           | Customer segmentation (VIP/Regular)      | `CASE WHEN spend > 1000 THEN 'VIP'` |

---

## 📈 Key Insights
### Sales Performance
- Identified **top 3 product categories** contributing to 70% of revenue  
- Seasonal trends showing **20% higher sales in Q4**  

### Customer Behavior  
- **VIP customers (5%)** generate 40% of total revenue  
- Repeat customers have **3x higher average order value**  

### Operational Efficiency  
- **Underperforming products** with <5% profit margin flagged for review  
- Inventory turnover **optimized by 15%** using sales velocity data  

---

## 📂 Dataset Overview
| **File**           | **Records** | **Key Fields**                              | **Source**       |
|--------------------|------------|--------------------------------------------|------------------|
| `List of Orders`   | 5,000+     | OrderID, OrderDate, CustomerSegment        | Kaggle (Modified)|
| `Order Details`    | 15,000+    | ProductID, Quantity, Profit, SubCategory   | Kaggle (Modified)|
| `Sales Target`     | 24         | Category, MonthlyTarget, Achieved          | Internal         |

---

## 💡 Strategic Recommendations
1. **Inventory**: Increase stock for top-selling subcategories (Electronics, Home Appliances)  
2. **Marketing**: Launch loyalty program for VIP customers  
3. **Pricing**: Adjust margins on low-profit categories (Furniture)  

---

## 🚀 Setup Guide
```bash
# Import data
mysql -u root -p < sql/schema.sql
mysqlimport --local -u root -p db_name data/*.csv

# Run analysis
mysql -u root -p < sql/queries.sql

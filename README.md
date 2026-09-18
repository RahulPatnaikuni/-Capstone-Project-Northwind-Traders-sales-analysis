# Capstone-Project-Northwind-Traders-sales-analysis
A comprehensive Power BI project showcasing data modeling, DAX, and visualization for analyzing global sales performance with the Northwind dataset.
# 📊 Power BI Sales Performance Dashboard – Northwind Traders

An **interactive Power BI dashboard** built using the **Northwind Traders dataset**, designed to analyze and visualize key business metrics such as **Total Sales**, **Orders**, **Customer Distribution**, **Product Performance**, and **Employee Efficiency**.  
This project demonstrates how raw data can be transformed into meaningful insights using **Power BI**, **DAX**, and a **Star Schema** data model.

---

## 🧾 Project Overview

The **Sales Performance Dashboard** provides a 360° view of business performance for Northwind Traders — a fictional global food trading company.  
The dashboard helps management track KPIs, identify trends, and make data-driven decisions.

### 🎯 Objectives:
- Visualize overall **sales trends** and **profit performance**.  
- Identify **top customers**, **best-selling products**, and **high-performing employees**.  
- Analyze **regional sales** and **shipping efficiency**.  
- Provide a modern, interactive Power BI dashboard for decision-makers.

---

## 🧩 Dataset Description

The project uses the **Northwind Database**, which contains sales and operations data for a trading company that imports and exports specialty foods worldwide.

### **Tables Used:**
| Table | Description |
|--------|--------------|
| **Customers** | Stores customer details such as company name, contact, and location. |
| **Employees** | Contains employee info like name, title, and hire date. |
| **Orders** | Includes customer orders with shipping and date details. |
| **Order Details** | Product-level order data including quantity, price, and discount. |
| **Products** | Product catalog with price, stock, and category info. |
| **Categories** | Defines product categories for grouping. |
| **Suppliers** | Supplier company details. |
| **Shippers** | Shipping companies and contact info. |

---

## 🧮 DAX Measures and KPIs

| KPI | DAX Formula | Description |
|------|--------------|-------------|
| **Total Sales** | `SUMX('Order Details', [UnitPrice] * [Quantity] * (1 - [Discount]))` | Calculates total revenue. |
| **Total Orders** | `COUNTROWS(Orders)` | Number of orders placed. |
| **Average Order Value** | `[Total Sales] / DISTINCTCOUNT(Orders[OrderID])` | Average sales per order. |
| **Total Customers** | `DISTINCTCOUNT(Customers[CustomerID])` | Unique customers count. |
| **Top Performer (Employee)** | `TOPN(1, SUMMARIZE(Employees, Employees[FullName], "Sales", [Total Sales]), [Total Sales], DESC)` | Identifies top sales employee. |

---

## 📊 Dashboard Pages

| Page | Description |
|------|--------------|
| **Overview** | Key KPIs and high-level business summary. |
| **Product Performance** | Product and category-level revenue insights. |
| **Customer Analysis** | Sales by customer, country, and segment. |
| **Employee Performance** | Employee-wise sales and top performer analysis. |
| **Order Analysis** | Order volume, shipping duration, and freight cost insights. |

---

## 🧱 Data Model Overview

The dashboard follows a **Star Schema** structure for efficient data relationships:

**Fact Tables:**  
- Orders  
- Order Details  

**Dimension Tables:**  
- Customers  
- Employees  
- Products  
- Categories  
- Suppliers  
- Shippers  

**Relationships:**  
- Customers[CustomerID] → Orders[CustomerID]  
- Employees[EmployeeID] → Orders[EmployeeID]  
- Orders[OrderID] → Order Details[OrderID]  
- Products[ProductID] → Order Details[ProductID]  
- Categories[CategoryID] → Products[CategoryID]  
- Suppliers[SupplierID] → Products[SupplierID]  
- Shippers[ShipperID] → Orders[ShipVia]

---

## 💡 Key Insights

- **USA and Germany** are the top revenue-generating countries.  
- **Beverages** and **Condiments** dominate category sales.  
- **Senior employees** outperform newer sales representatives.  
- **Q4** shows consistent peaks in order volume.  
- High-value customers contribute significantly to total revenue.

---

## 🧰 Tools and Technologies

| Tool | Purpose |
|------|----------|
| **Power BI Desktop** | Dashboard design and DAX-based analytics. |
| **Excel / SQL** | Data extraction, cleaning, and transformation. |
| **Northwind Dataset** | Source data for analysis. |

---

## 🚀 How to Use

1. Clone or download the repository.  
2. Open the `.pbix` file in **Power BI Desktop**.  
3. Explore the dashboard pages interactively.  
4. (Optional) Connect your own dataset with the same schema for custom analysis.

---

## 🏁 Conclusion

The **Sales Performance Dashboard** provides an end-to-end Power BI solution for tracking and analyzing sales operations.  
It transforms static business data into **dynamic, visual insights**, empowering decision-makers to identify trends and opportunities effectively.

---

## 🔮 Future Enhancements

- Add **real-time data refresh** with Power BI Service.  
- Implement **forecasting and predictive analytics** using AI visuals.  
- Expand scope to include **inventory and supplier performance**.  
- Automate **report sharing and alerts** for stakeholders.

---

## 🙌 Author

**  Rahul Patnaikuni**  
🎓 *Btech/EEE/ Data Analytics Student*  
💼 *Passionate about Business Intelligence and Data Visualization*  
📧 patnaikunirahul@gmail.com

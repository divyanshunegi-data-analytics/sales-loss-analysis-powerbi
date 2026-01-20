# 📊 Sales & Loss Analysis Dashboard (MySQL + Power BI)

End-to-end data analytics project focused on **sales performance** and **loss analysis** using **MySQL** for data processing and **Power BI** for interactive dashboards.

---

## 🚀 Project Overview

This project analyzes retail sales data to:
- Track overall sales and profitability
- Identify loss-making regions, categories, and customers
- Understand the impact of discounts on profitability
- Provide actionable business insights using dashboards

The project follows an **industry-style workflow**:
**SQL → Data Cleaning → Feature Engineering → Power BI Dashboards**

---

## 📂 Dataset

- **Source:** Kaggle – Superstore Sales Dataset  
- **Format:** CSV  
- **Records:** ~9,700 rows  
- **Key Fields:**  
  Sales, Profit, Discount, Quantity, Customer, Product, Category, Region, Dates

This dataset represents a **real-world retail business use case**.

---

## 🗄️ Database Setup (MySQL)

1. Created database:
   ```sql
   CREATE DATABASE sales_db;
Created table superstore and imported CSV using
MySQL Table Data Import Wizard

Successfully loaded:

9,694 rows

All columns validated after import

🧹 Data Cleaning & Transformation (SQL)
🔹 Date Standardization
Original dates were in text format (MM/DD/YYYY).
Converted them into MySQL DATE format using:

sql
Copy code
STR_TO_DATE(order_date, '%m/%d/%Y')
🔹 Derived Date Columns
Created the following columns for time-based analysis:

order_year

order_month

order_month_no

order_quarter

year_month

shipping_days

🧮 Feature Engineering & KPIs (SQL)
Created calculated fields directly in SQL for dashboard usage:

profit_margin_pct

profit_status (Profit / Loss)

discount_flag

revenue_per_qty

total_loss (negative profit aggregation)

These columns were later used directly in Power BI visuals.

🔐 Authentication & Connectivity Handling
Faced MySQL authentication issues with default root user

Created a dedicated user:

sql
Copy code
CREATE USER 'pbi_user' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON sales_db.* TO 'pbi_user';
Followed enterprise-standard approach:

Installed MySQL ODBC Unicode Driver (64-bit)

Configured System DSN

Connected Power BI using ODBC connector

📊 Power BI Integration & Validation
Connected Power BI to MySQL via ODBC

Validated:

All 9,694 rows loaded correctly

Data types and calculated columns intact

Created DAX measures for:

Total Sales

Total Profit

Total Loss

Profit Margin %

Loss Orders

Loss Customers

📈 Dashboards Created
🟦 1. Sales Performance Dashboard
Focus: Growth, revenue, profitability

Key visuals:

KPI Cards (Sales, Quantity, Profit)

Sales trend by year

Sales by region & product

Customer-wise sales table

Profit margin gauge

Interactive slicers (Year, Category, Region, Segment)

📸 Screenshot:

bash
Copy code
sales_dashboard.png
🔴 2. Loss Analysis Dashboard
Focus: Loss drivers & discount impact

Key insights:

Total business loss overview

Loss by region & sub-category

Top loss-making customers

Discount vs Profit scatter analysis

Identification of high-discount loss zones

📸 Screenshot:

bash
Copy code
loss_dashboard.png
💡 Key Business Insights
Furniture category suffers the highest losses due to heavy discounting

A small set of customers contributes disproportionately to total losses

Higher discounts often lead to negative profitability

Certain regions consistently underperform in profit

🛠️ Tools & Technologies
MySQL – Data storage, cleaning & feature engineering

Power BI – Data modeling, DAX, dashboards

ODBC Connector – Secure database connectivity

GitHub – Version control & project documentation

📁 Repository Structure
bash
Copy code
sales-loss-analysis-powerbi/
│
├── dashboards/
│   ├── sales_dashboard.png
│   └── loss_dashboard.png
│
├── sales_performance_dashboard.pbix
├── sql_dashboard/        # SQL scripts & queries
├── README.md
📌 Learning Outcomes
End-to-end SQL → Power BI project execution

Real-world data cleaning and KPI creation

Handling database authentication & connectivity issues

Designing insight-driven dashboards for stakeholders

👤 Author
Divyanshu Negi
Aspiring Data Analyst | SQL | Power BI | Data Visualization

⭐ If you like this project, feel free to star the repository!

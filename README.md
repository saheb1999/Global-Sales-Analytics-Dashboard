# ![download (1)]([https://github.com/saheb1999/Global-Sales-Analytics-Dashboard/blob/main/Github_sales%20image.png])
# 🌍 Global Sales Analytics Dashboard  
### ** EXCEL + SQL + Power BI | End-to-End Data Analysis Project**

This repository contains my complete **Global Sales Analytics** project, built using **MySQL**, **DAX**, and **Power BI**.  
It analyzes sales transactions across **7 countries**, **500+ stores**, **multiple product categories**, and **diverse customer groups**.

---

## 📌 Project Overview

The goal of this project is to transform raw sales records into meaningful business insights using:

- **SQL** for data cleaning, transformation & model preparation  
- **DAX** for advanced calculations (YTD, YOY, QoQ, Rolling 12M)  
- **Power BI** for a fully interactive multi-page dashboard  

This project covers **Sales**, **Profit**, **Customers**, **Products**, **Stores**, and **Time Intelligence** analysis.

---

## 📊 Dashboard Pages

### **1️⃣ Home Page – Summary**
- Total Sales, Total Profit, Total Orders  
- Discounts Given, Average Order Value  
- Business Highlights Section  
- Navigation buttons

### **2️⃣ Overview Page**
- Sales by Country  
- Sales by Month  
- Profit by Country  
- Sales Split by Payment Method  

### **3️⃣ Customer Insights**
- Sales by Age Group  
- Profit by Gender  
- Category Discounts  
- Discounts by Payment Method  
- Average Quantity & Profit per Order  

### **4️⃣ Product & Store Performance**
- Top Store Location  
- Top Category by Sales  
- Top Product by Sales  
- Number of Stores  
- Top 10 Products by Sales & Profit  
- Sales by Store Location (Treemap)

### **5️⃣ Time Intelligence & Trends**
- YTD Sales & YTD Profit  
- YoY & QoQ Growth  
- Monthly Revenue Trend  
- Rolling 12-Month Sales Trend  
- Quarterly Comparison  

---

## 🧮 Key DAX Measures

Some important measures used:

```DAX
Total Sales = SUM(master_sales_data[Total_Amount])

Total Profit = SUM(master_sales_data[Profit])

Total Orders = DISTINCTCOUNT(master_sales_data[Order_ID])

Avg Order Value = [Total Sales] / [Total Orders]

Sales YTD = TOTALYTD([Total Sales], 'Date_Table'[Date])

Profit YTD = TOTALYTD([Total Profit], 'Date_Table'[Date])

YoY Growth % = 
VAR PrevYear = CALCULATE([Total Sales], DATEADD('Date_Table'[Date], -1, YEAR))
RETURN ([Total Sales] - PrevYear) / PrevYear

QoQ Growth % =
VAR PrevQ = CALCULATE([Total Sales], DATEADD('Date_Table'[Date], -1, QUARTER))
RETURN ([Total Sales] - PrevQ) / PrevQ

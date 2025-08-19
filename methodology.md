# 🛠️ Methodology – Retail Sales Analysis Dashboard

This document explains the step-by-step process followed to design and build the **Retail Sales Analysis Dashboard** using **Power BI**.

---

## 1️⃣ Data Collection
- Gathered sales data from **multiple sources**:
  - **Excel/CSV files** containing sales, wages, and rent details.
  - **SQL database queries** for historical sales and target values.
- Datasets included:
  - Store information (ID, location, type, size).
  - Sales data (date, department, revenue, margin).
  - Targets (monthly/yearly sales goals).
  - Operational data (wages, rent, expenses).

---

## 2️⃣ Data Cleaning & Transformation
- Performed in **Power Query (M Language)** within Power BI:
  - Removed duplicates and null values.
  - Standardized formats (dates, currency, percentages).
  - Created calculated columns for **Gross Margin**, **Difference from Target**, etc.
  - Merged multiple tables (Sales, Store Info, Targets) using **joins**.

---

## 3️⃣ Data Modeling
- Built a **star schema** with:
  - **Fact Table** → Sales (Revenue, Quantity, Targets, Wages, Rent).
  - **Dimension Tables** → Store, Department, Date.
- Established relationships:
  - Date → Sales (for time-series analysis).
  - Store → Sales (for geographic & type analysis).
  - Department → Sales (for category-wise breakdown).

---

## 4️⃣ DAX Measures
Created custom **DAX (Data Analysis Expressions)** measures:
- **Total Sales** = `SUM(Sales[Revenue])`
- **Gross Margin** = `SUM(Sales[Revenue]) - SUM(Sales[Cost])`
- **Sales YTD** = `TOTALYTD([Total Sales], Date[Date])`
- **Difference from Target** = `[Total Sales] - [Target Sales]`

---

## 5️⃣ Dashboard Design
- **Page 1 – Sales Overview**
  - KPI cards for **Sales YTD, Total Sales, Gross Margin**.
  - Sales breakdown by **Store Location, Department, and Store Type**.
  - Map visualization for **geographic performance**.

- **Page 2 – Performance & Operations**
  - Sales vs Target tracker with variance indicators.
  - Store-level table with **Wages, Sales, and Target Differences**.
  - Scatter plot for **Store Size vs Rent** comparison.

---

## 6️⃣ Insights
- Core stores dominate with ~75% of sales.  
- Digital stores are growing but remain under 1bn revenue.  
- Some states (e.g., Connecticut, Indiana) are exceeding targets.  
- Rent and store size show strong correlation for **Core stores**.

---

## 7️⃣ Deployment
- Dashboard published to **Power BI Service** for stakeholders.  
- Enabled scheduled refresh for automated updates.  
- Role-based access implemented for management vs store-level teams.

---

## 8️⃣ Future Enhancements
- Integrate **Python/R scripts** for predictive analytics.  
- Add **customer segmentation dashboards**.  
- Build **automated alerts** for underperforming stores.  

---

✍️ **Author:** Avani Gaikwad  

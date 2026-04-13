# 🌾 AgriData ETL Pipeline

## 📌 Overview
This project implements a complete **End-to-End Data Engineering Pipeline** for agricultural data using **SSIS (SQL Server Integration Services)** and **Power BI**.

The solution integrates data from multiple heterogeneous sources, performs data cleaning and validation, and generates meaningful insights through interactive dashboards.

---

## 🎯 Objectives
- Integrate data from multiple sources (Excel, CSV, TXT)
- Clean and standardize inconsistent data
- Validate data using reference tables (Lookup)
- Handle invalid and unmatched records
- Load structured data into SQL Server
- Visualize insights using Power BI

---

## 📂 Data Sources
The dataset is collected from different file formats:

- 📄 Dist1.xlsx → Excel Source  
- 📄 Dist2.csv → CSV File  
- 📄 Dist3.txt → Flat File  

---

## 🗃 Dataset Schema

| Column Name | Description |
|------------|------------|
| Date | Record date |
| Location | Indian state |
| Crop | Type of crop |
| Soil_Moisture | Soil moisture level |
| Temperature_C | Temperature (°C) |
| Yield_kg_per_hectare | Crop yield |

---

## ⚠️ Data Challenges
- Multiple file formats (Excel, CSV, TXT)
- Inconsistent date formats (7-digit / 8-digit)
- Data type mismatches
- Invalid crop values

---

## ⚙️ ETL Pipeline (SSIS)

### 🔹 Extract
- Data is extracted from:
  - Excel Source
  - Flat File Source (CSV & TXT)

---

### 🔹 Transform

#### ✅ Data Conversion
- Standardizes all columns to a consistent data type (Unicode)

#### ✅ Derived Column
- Formats and cleans date values
- Creates new transformed columns

#### ✅ Conditional Split
- Splits data based on date format:
  - 7-digit dates
  - 8-digit dates

#### ✅ Derived Column (Post-Split)
- Fixes each date format separately

#### ✅ Union All
- Merges all processed data streams

#### ✅ Lookup (Data Validation)
- Validates crop values using a reference table
- ✔ Valid records → continue  
- ❌ Invalid records → redirected to error file  

---

### 🔹 Load
- Data is loaded into SQL Server using:
  - OLE DB Destination

#### Additional Tasks:
- Execute SQL Task → Truncate table before load  
- Row Count → Count processed rows  
- Sort → Organize data  

---

## 🚨 Error Handling
- Invalid records are redirected using:
  - Lookup No Match Output
- Stored in:
  - LookupNoMatch.txt

---

## 🧱 SSIS Components Used
- Excel Source  
- Flat File Source  
- Data Conversion  
- Derived Column  
- Conditional Split  
- Lookup  
- Union All  
- Row Count  
- Sort  
- OLE DB Destination  

---

## 📊 Power BI Dashboard

The project includes an interactive dashboard with multiple visualizations:

### 📌 KPI Cards
- Average Yield  
- Total Records  
- High Yield Count  
- Average Temperature  

---

### 📈 Visualizations

1. Bar Chart – Yield by Crop  
2. Pie Chart – Crop Distribution  
3. Line Chart – Yield Over Time  
4. Tree Map – Yield by Location and Crop  
5. Column Chart – Seasonal Yield  
6. Bar Chart – Yield Category (High/Medium/Low)  
7. Waterfall Chart – Location Contribution  

---

## 📈 Key Insights
- Tomato has the highest yield among crops  
- Agricultural yield varies by location  
- Seasonal changes impact productivity  
- Most records fall into high-yield category  

---

## 🛠 Technologies Used
- Microsoft SQL Server  
- SSIS (SSDT)  
- Power BI  

---

## 🚀 Future Improvements
- Implement Incremental Load  
- Add real-time data streaming  
- Improve validation rules  
- Apply predictive analytics  

---

## 👤 Author
Ahmed Ibrahim

---

## ⭐ Final Note
This project demonstrates a real-world Data Engineering workflow including ETL, data validation, and business intelligence visualization.

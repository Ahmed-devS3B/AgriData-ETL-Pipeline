# \# 🌾 AgriData ETL Pipeline

# 

# \## 📌 Overview

# This project presents an \*\*end-to-end Data Engineering pipeline\*\* that integrates agricultural data from multiple heterogeneous sources using \*\*SSIS (SQL Server Integration Services)\*\* and visualizes insights using \*\*Power BI\*\*.

# 

# The solution demonstrates a real-world implementation of the \*\*ETL process (Extract, Transform, Load)\*\* including data cleaning, transformation, validation, and visualization.

# 

# \---

# 

# \## 🎯 Objectives

# \- Integrate data from multiple sources (Excel, CSV, TXT)

# \- Clean and standardize inconsistent data

# \- Validate data using a reference table

# \- Handle errors and invalid records

# \- Load structured data into SQL Server

# \- Generate insights using Power BI dashboards

# 

# \---

# 

# \## 📂 Data Sources

# The project uses three different datasets:

# 

# \- 📄 \*\*Dist1.xlsx\*\* → Excel Source  

# \- 📄 \*\*Dist2.csv\*\* → CSV File  

# \- 📄 \*\*Dist3.txt\*\* → Flat File  

# 

# \---

# 

# \## 🗃 Dataset Structure

# 

# | Column Name | Description |

# |------------|------------|

# | Date | Record date |

# | Location | Indian state |

# | Crop | Type of crop |

# | Soil\_Moisture | Soil moisture level |

# | Temperature\_C | Temperature (°C) |

# | Yield\_kg\_per\_hectare | Crop yield |

# 

# \---

# 

# \## ⚠️ Data Challenges

# \- Multiple file formats (Excel, CSV, TXT)

# \- Inconsistent date formats (7-digit / 8-digit)

# \- Data type mismatches (Unicode issues)

# \- Invalid or unmatched crop values

# 

# \---

# 

# \## ⚙️ ETL Pipeline (SSIS)

# 

# \### 🔹 1. Extract

# \- Data is extracted from:

# &#x20; - Excel Source

# &#x20; - Flat File Source (CSV \& TXT)

# 

# \---

# 

# \### 🔹 2. Transform

# 

# \#### ✅ Data Conversion

# \- Standardizes all columns to consistent data types (Unicode)

# 

# \#### ✅ Derived Column

# \- Formats date into a unified structure

# \- Creates new transformed columns

# 

# \#### ✅ Conditional Split

# \- Separates records based on date length:

# &#x20; - 7-digit format

# &#x20; - 8-digit format

# 

# \#### ✅ Derived Column (Post-Split)

# \- Fixes each date format separately

# 

# \#### ✅ Union All

# \- Merges all processed data streams into one dataset

# 

# \#### ✅ Lookup (Data Validation)

# \- Validates `Crop` values against a reference table

# \- ✔ Match → continues processing  

# \- ❌ No Match → redirected to error file

# 

# \---

# 

# \### 🔹 3. Load

# \- Data is loaded into SQL Server using:

# &#x20; - \*\*OLE DB Destination\*\*

# 

# \#### Additional Tasks:

# \- \*\*Execute SQL Task\*\* → Truncate table before loading (Initial Load)

# \- \*\*Row Count\*\* → Counts processed rows

# \- \*\*Sort\*\* → Organizes data before loading

# 

# \---

# 

# \## 🚨 Error Handling

# \- Invalid crop values are redirected using:

# &#x20; - \*\*Lookup No Match Output\*\*

# \- Stored in:

# &#x20; - `LookupNoMatch.txt`

# 

# \---

# 

# \## 🧱 SSIS Components Used

# 

# | Component | Purpose |

# |----------|--------|

# | Excel Source | Read Excel data |

# | Flat File Source | Read CSV/TXT files |

# | Data Conversion | Fix data types |

# | Derived Column | Create/modify columns |

# | Conditional Split | Separate data |

# | Lookup | Validate data |

# | Union All | Merge data |

# | Row Count | Count rows |

# | Sort | Organize data |

# | OLE DB Destination | Load into SQL Server |

# 

# \---

# 

# \## 📊 Power BI Dashboard

# 

# The project includes an interactive dashboard with multiple visualizations:

# 

# \### 📌 KPI Indicators

# \- Average Yield

# \- Total Records

# \- High Yield Count

# \- Average Temperature

# 

# \---

# 

# \### 📈 Visualizations

# 

# 1\. \*\*Bar Chart – Yield by Crop\*\*  

# &#x20;  → Compares productivity across crops  

# 

# 2\. \*\*Pie Chart – Crop Distribution\*\*  

# &#x20;  → Shows proportion of each crop  

# 

# 3\. \*\*Line Chart – Yield Over Time\*\*  

# &#x20;  → Displays trends and seasonal changes  

# 

# 4\. \*\*Tree Map – Yield by Location and Crop\*\*  

# &#x20;  → Shows hierarchical distribution  

# 

# 5\. \*\*Column Chart – Seasonal Yield\*\*  

# &#x20;  → Compares yield across seasons  

# 

# 6\. \*\*Bar Chart – Yield Categories\*\*  

# &#x20;  → Classifies data into High / Medium / Low  

# 

# 7\. \*\*Waterfall Chart – Location Contribution\*\*  

# &#x20;  → Shows cumulative yield contribution  

# 

# \---

# 

# \## 📈 Key Insights

# \- Tomato has the highest yield among crops  

# \- Yield varies significantly by location  

# \- Seasonal changes impact agricultural productivity  

# \- Most records fall into the high-yield category  

# 

# \---

# 

# \## 🛠 Technologies Used

# \- Microsoft SQL Server

# \- SSIS (SQL Server Integration Services)

# \- Power BI

# 

# \---

# 

# \## 🚀 Future Improvements

# \- Implement Incremental Load instead of full load  

# \- Add real-time data streaming  

# \- Enhance validation rules  

# \- Apply predictive analytics (ML models)  

# 

# \---

# 

# \## 👤 Author

# \*\*Ahmed Ibrahim\*\*

# 

# \---

# 

# \## ⭐ Project Highlights

# ✔ Multi-source data integration  

# ✔ Data cleaning and transformation  

# ✔ Data validation using Lookup  

# ✔ Error handling and data quality  

# ✔ Interactive dashboard and insights  

# 

# \---

# 

# \## 📌 Final Note

# This project reflects a \*\*Data Engineering pipeline\*\* and demonstrates strong understanding of:

# \- ETL Processes  

# \- Data Integration  

# \- Data Cleaning \& Validation  

# \- Business Intelligence  


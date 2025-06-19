# Adventure-Sales-Data-Analysis-Power-BI

An interactive Power BI report built using the AdventureWorks dataset, designed to deliver actionable insights into product performance, sales trends, customer behavior, and returns. This project demonstrates key BI practices such as data modeling, DAX calculations, and dashboard storytelling.

---

## 🗂 Project Structure

AdventureWorks-PowerBI/
│
├── Dataset/
│ └── AdventureWorksDW2020.bak
│
├── PowerBI_File/
│ └── AdventureWorks_Dashboard.pbix
│
├── Screenshots/
│ ├── dashboard-overview.png
│ └── model-view.png
│
└── README.md

---

## 🎯 Project Objective

- Build a professional, clean Power BI report using real-world relational data.
- Design a star schema model optimized for performance and usability.
- Develop calculated KPIs using DAX.
- Deliver compelling visuals and user-friendly navigation for insights.

---

## 📈 Dashboard Overview

![Screenshot 2025-06-19 081950](https://github.com/user-attachments/assets/d1674d29-e432-483d-a981-6b336a1baead)


### 🔹 KPIs (Top Cards)
- 💰 **Revenue**: $24.9M  
- 📈 **Profit**: $10.5M  
- 📦 **Orders**: 25.2K  
- 🔁 **Return Rate**: 2.2%

### 📊 Revenue Trending
Interactive line chart visualizing monthly revenue growth from Jan 2020 to 2022, featuring:
- Trend line & confidence band
- Time-based slicer for user-driven filtering

### 🗃 Orders by Category
Bar chart split by:
- Accessories – 17.0K orders  
- Bikes – 13.9K orders  
- Clothing – 7.0K orders

### 🏆 Top 10 Products Table
Shows product-wise:
- Total orders
- Revenue generated
- Return rate (with conditional formatting)

### 📅 Monthly KPIs
- **Monthly Revenue**: $1.83M (+3.31%)  
- **Monthly Orders**: 2,146 (-0.88%)  
- **Monthly Returns**: 166 (+1.78%)

### 🟢 Product Highlights
- **Most Ordered Product Type**: Tires and Tubes  
- **Most Returned Product Type**: Shorts

---

## 🧠 Data Model (Star Schema)

![Screenshot 2025-06-19 114011](https://github.com/user-attachments/assets/4012f9ed-3e17-4528-a38f-2f8d5f70d0e0)


### 📊 Fact Tables
- `Sales Data`: Order-level transactions with `CustomerKey`, `OrderDate`, etc.
- `Returns Data`: Tracks returned products.

### 🧾 Dimension Tables
- `Calendar Lookup`: Full date hierarchy (Day, Month, SWITCH logic for custom month ordering)
- `Customer Lookup`: Attributes like education, region, domain
- `Territory Lookup`: Regional segmentation
- `Product Lookup`: Product-level metadata
- `Product Subcategories Lookup`
- `Product Categories Lookup`

### 📏 Measure Table
Centralized table for all calculated measures like:
Total Revenue = SUM('Sales Data'[SalesAmount])

Profit = [Total Revenue] - SUM('Sales Data'[ProductCost])

Return Rate = DIVIDE([Total Returns], [Total Orders])

YoY Revenue = CALCULATE([Total Revenue], SAMEPERIODLASTYEAR('Calendar Lookup'[Date]))

<details>
  <summary>📚 Key Learnings</summary>

Through this project, the following skills and best practices were learned and applied:

- ✅ **Star Schema Modeling**: Designed a clean and efficient star schema data model using fact and dimension tables, optimizing for performance and clarity.
- ✅ **Advanced DAX Implementation**: Applied DAX functions such as `CALCULATE`, `DIVIDE`, and `SAMEPERIODLASTYEAR` to compute key metrics like profit, YoY revenue, and return rate.
- ✅ **Business Intelligence Storytelling**: Created dashboards that visually narrate business performance, allowing end-users to make informed decisions at a glance.
- ✅ **Data Optimization in Power BI**: Organized the data model with hidden fields, grouped measures, cleaned relationships, and used user-friendly slicers to enhance the report experience.

</details>


<details>
  <summary>🛠 Tools Used</summary>

This project was built using the following tools and technologies:

- 🧩 **Power BI Desktop**  
  Used for data modeling, building relationships, and designing interactive visual reports with slicers, KPIs, and custom visuals.

- 🗃️ **AdventureWorksDW2020 Dataset**  
  Microsoft's sample SQL Server Data Warehouse, used to simulate a real-world business scenario with fact and dimension tables.

- 📊 **DAX (Data Analysis Expressions)**  
  Language used in Power BI to build calculated columns and measures for KPIs, time intelligence (like YoY), and return rates.

</details>



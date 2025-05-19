# 🛍️ Maven Market Dashboard – Power BI

A complete end-to-end Power BI project focused on cleaning, transforming, modeling, and analyzing sales and customer data for a fictional retail chain. The dashboard presents key performance metrics such as transactions, profit, return rates, and revenue trends, with interactive visuals and advanced DAX calculations for dynamic business intelligence.

---

## 📁 Dataset Overview

The project is based on 7 structured CSV files and 1 folder of transactional data:

- **Customers** – 1,000+ records including demographics and loyalty program data
- **Products** – 49 rows with pricing, profit margins, and product categorization
- **Stores & Regions** – Information about store locations and hierarchy
- **Calendar** – Full date table enriched with week/month/quarter/year logic
- **Transactions** – Merged data from 1997 and 1998 sales logs (~270K records)
- **Returns** – Details on product returns (~7K records)

---

## 🔧 Project Workflow

### 🧩 Part 1: Connecting & Shaping the Data (Power Query Editor)
- Connected to multiple CSVs and folder data
- Applied data types, cleaned nulls, replaced values
- Created new columns (e.g., `full_name`, `birth_year`, `discount_price`, `full_address`, `area_code`)
- Merged datasets using XLOOKUP-style transformations (`INDEX`, `SEARCH`, `IF`)
- Added temporal features: start of week/month, quarter, day name

### 🔗 Part 2: Building the Data Model
- Created a star schema with **Transaction_Data** and **Return_Data** as fact tables
- Linked to dimension tables (Calendar, Customers, Products, Stores, Regions)
- Ensured clean **1-to-many** relationships with correct filter flow
- Categorized geographic columns for mapping visuals
- Formatted key fields (dates, currency, postal codes)

### 📊 Part 3: DAX Measures & KPIs
Implemented over 20 calculated columns and measures, including:

- **Sales & Returns**
  - `Quantity Sold`, `Quantity Returned`
  - `Total Transactions`, `Total Returns`
  - `Return Rate`, `% Weekend Transactions`

- **Financials**
  - `Total Revenue`, `Total Cost`, `Total Profit`, `Profit Margin`
  - `YTD Revenue`, `60-Day Revenue`, `Last Month Revenue`
  - `Revenue Target` (5% above prior month)

- **Customer & Product Intelligence**
  - `Current Age`, `Priority`, `Price Tier`, `Short_Country`
  - `Unique Products`

All measures were tested via matrix visuals to match expected values (e.g., `$1.76M` revenue, `59.67%` margin).

### 📈 Part 4: Report Design
The final report, titled **"Topline Performance"**, includes:

- **Matrix Visual**: KPIs by product brand with conditional formatting
- **KPI Cards**: Current vs. last month for Transactions, Profit, and Returns
- **Map + Treemap**: Store performance by city and drillable regions
- **Line Chart**: Weekly revenue trend (1998 only)
- **Gauge Chart**: Revenue vs. dynamic monthly target

Interactivity includes:
- Slicers for region, drill-down visuals, Top N filters, and dynamic YTD / 60-day calculations
- Visuals respond to filter context via slicers and date relationships

---

## 🧠 Key Features & Techniques

- ✅ Star schema with lookup and fact tables
- ✅ Power Query transformations: merging, formatting, grouping, custom columns
- ✅ DAX for time intelligence: `DATESYTD`, `DATESINPERIOD`, `DATEADD`
- ✅ Visual-level filters, report-level filters, Top N filtering
- ✅ Conditional formatting in matrix visuals
- ✅ Timeline analysis & forecasting via revenue target logic

---

## 📌 Use Case

This project simulates an **executive-level sales and operations dashboard** for a retail chain, useful for:

- **Sales leaders** tracking YTD performance, top products, and revenue trends
- **Store managers** identifying top-performing cities and regions
- **Operations analysts** understanding return rates and profit margins
- **Executives** setting monthly targets and monitoring performance goals

---

## 🖼️ Screenshots

![image](https://github.com/user-attachments/assets/de4b7bdc-4066-4dc5-a21e-a126be6d228b)


---

## 📂 Files Included

- `MavenMarket_report.pbix` – Full Power BI file
-  `maven-market-raw-data.zip` - Raw data files
- README.md (this file)

---

## 🚀 Future Improvements

- Add tooltip pages for better data storytelling
- Build bookmarks and buttons for drill-through navigation
- Include customer segmentation insights and loyalty program trends
- Automate data refresh from cloud source

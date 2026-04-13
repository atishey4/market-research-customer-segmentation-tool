# 📊 Market Research & Customer Segmentation Tool — Advanced Excel Project

> **MBA Portfolio Project | Customer Analytics | RFM Analysis | Marketing Intelligence**

![Excel](https://img.shields.io/badge/Tool-Microsoft%20Excel-217346?style=flat&logo=microsoft-excel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Domain](https://img.shields.io/badge/Domain-Customer%20Analytics-blue)

---

## ⬇️ Download Project Files

| File | Description | Link |
|------|-------------|------|
| 📊 Excel Workbook | Full segmentation tool with all sheets & dashboard | [Download Excel](https://github.com/atishey4/market-research-customer-segmentation-tool/raw/main/Market_Research_Customer_Segmentation_Tool_Enhanced-5.xlsx) |

---

## 📸 Screenshots

### Interactive Dashboard — KPI Cards, Charts & Slicers
![Interactive Dashboard](screenshots/Screenshot-2026-04-13-180954.jpg)

### KPI Reference Table, Segment Performance Summary & Timeline Filter
![KPI Reference & Segment Summary](screenshots/Screenshot-2026-04-13-181329.jpg)

### KPI Summary Sheet — Revenue, Customer & Segment KPIs
![KPI Summary Sheet](screenshots/Screenshot-2026-04-13-181205.jpg)

---

## 📌 Project Objective

To create an Excel-based tool that collects, cleans, and analyzes customer survey and transaction data, applies multi-layered segmentation (RFM analysis, demographic, and behavioral), and generates an interactive dashboard that guides marketing strategy and customer targeting decisions.

---

## 🏢 Industry Relevance

Customer segmentation is a cornerstone of modern marketing. Companies like **Amazon, Flipkart, Nielsen, and Kantar** rely on segmentation tools to understand customer groups, predict buying behavior, and personalize campaigns. The customer analytics market is expected to surpass **$35B by 2030**, growing at 18% CAGR. This type of tool is actively used by Marketing Analysts, Business Analysts, Product Managers, and CRM Specialists.

---

## 🛠️ Tools & Technologies Used

| Tool | Purpose |
|------|---------|
| Microsoft Excel | Core platform for data, formulas, and dashboard |
| Power Query | Data import, cleaning, and standardization |
| PivotTables | Dynamic customer and revenue aggregation |
| Excel Charts | Bar, column, donut, line, and pie visualizations |
| Slicers & Timeline | Interactive segment and region filtering |
| SUMIFS, COUNTIFS, IF, IFS, IFERROR | KPI and segmentation logic |
| XLOOKUP / INDEX-MATCH | Customer data lookups |
| RANK.EQ, PERCENTILE | RFM quintile scoring |
| Conditional Formatting | High-value customer highlights |
| VBA Macro (optional) | One-click dashboard refresh |

---

## 📁 Folder Structure

```
market-research-customer-segmentation-tool/
│
├── Market_Research_Customer_Segmentation_Tool_Enhanced-5.xlsx   # Main Excel workbook
│
├── screenshots/
│   ├── Screenshot-2026-04-13-180954.jpg   # Interactive Dashboard
│   ├── Screenshot-2026-04-13-181329.jpg   # KPI Reference Table & Segment Performance Summary
│   └── Screenshot-2026-04-13-181205.jpg   # KPI Summary Sheet
│
├── LICENSE
└── README.md
```

---

## 📊 Dataset Description

The dataset covers **FY 2025–26 (Apr 2025 – Mar 2026)** with **200 customers** across **1,044 transactions**, spanning **7 product categories** and **23 cities/regions**.

### Customers Table (`tblCustomers`)
| Column | Description |
|--------|-------------|
| Customer ID | Unique identifier |
| Name | Customer full name |
| Gender | Male / Female |
| Age | Customer age |
| City / Region | Geographic location (23 cities) |
| Income Range | Annual income bracket |
| Join Date | Customer acquisition date |

### Transactions Table (`tblTransactions`)
| Column | Description |
|--------|-------------|
| Transaction ID | Unique transaction reference |
| Customer ID | Linked customer |
| Date | Purchase date |
| Product Category | 7 categories including Electronics, FMCG, Apparel, Furniture, Software |
| Amount | Transaction value (INR) |

### Survey Table (`tblSurvey`)
| Column | Description |
|--------|-------------|
| Customer ID | Linked customer |
| Satisfaction Score | Rating 1–5 |
| Preferred Channel | Online / Offline |
| Recommendation Likelihood | Score 1–10 |

---

## 📋 Excel Sheet Structure

| Sheet | Purpose |
|-------|---------|
| `RawData` | Original unprocessed customer, transaction & survey data |
| `CleanedData` | Standardized and validated data (TRIM, PROPER, deduplication) |
| `RFM_Analysis` | Recency, Frequency, Monetary scoring and quintile ranking |
| `SegmentationLogic` | Rule-based segment assignment using IFS formulas |
| `KPI_Summary` | Aggregated KPI table by segment, region, and channel |
| `Dashboard` | Interactive visual customer segmentation dashboard |

---

## 🔢 Key Excel Formulas Used

```excel
# Recency (days since last purchase)
= TODAY() - MAXIFS(tblTransactions[Date], tblTransactions[CustomerID], [@CustomerID])

# Frequency (number of transactions)
= COUNTIFS(tblTransactions[CustomerID], [@CustomerID])

# Monetary (total spend)
= SUMIFS(tblTransactions[Amount], tblTransactions[CustomerID], [@CustomerID])

# Age Group Classification
= IF([@Age]<25,"<25", IF([@Age]<40,"25-39", IF([@Age]<55,"40-54","55+")))

# Income Bracket
= IF([@IncomeRange]<25000,"Low", IF([@IncomeRange]<50000,"Mid","High"))

# Satisfaction Index
= AVERAGE([@Satisfaction], [@RecommendationLikelihood]/2)

# Segment Assignment
= IFS(
    [@RFM]="555", "Loyal",
    AND([@Recency]>90, [@Frequency]<3), "At Risk",
    AND([@Monetary]<5000, [@Frequency]>=5), "Bargain Seeker",
    TRUE, "General"
  )
```

---

## 📈 Key KPIs Tracked

- ✅ **Total Customers** — 200 across 23 cities/regions
- ✅ **Total Revenue (INR)** — ₹1,00,38,773
- ✅ **Average Order Value (AOV)** — ₹9,616
- ✅ **Total Transactions** — 1,044
- ✅ **Repeat Customer %** — 57.5% (115 returning customers)
- ✅ **Active Customers** — 78 (last purchase within period)
- ✅ **Loyal Customers** — 17 (8.5% of base)
- ✅ **High Value Customers** — 74 (37.0% of base)
- ✅ **At-Risk Customers** — 38
- ✅ **Avg Satisfaction Score** — 3.19
- ✅ **Online Revenue %** — 47.2% | **Offline Revenue %** — 52.8%
- ✅ **Avg Purchase Frequency** — 5.22 transactions per customer

---

## 📊 Dashboard Features

### Visuals Included
- 📊 **Horizontal Bar Chart** — Customers by Segment (Loyal / High Value / General / Bargain Seeker / At Risk)
- 📊 **Column Chart** — Revenue by Segment (INR)
- 🍩 **Donut Chart** — Customer Distribution by Age Group (<25 / 25-39 / 40-54 / 55+)
- 📉 **Line Chart** — Monthly Total Revenue Trend (Apr 2025 – Mar 2026)
- 📋 **Segment Performance Summary Table** — Customers, Revenue, Revenue%, Avg Spend, Status (Retain / Upsell / Re-engage / Nurture / Grow)
- 📊 **KPI Reference Table** — Live-updating KPI summary grid
- 🎛️ **Slicers** — Purchase Channel, Customer Segment, City/Region
- 📅 **Timeline Filter** — Dynamic month-range filtering (Jan 2025 – May 2026)

---

## 💡 Business Insights Derived

1. **High Value dominates revenue** — 74 High Value customers generate 65.8% of total revenue (₹66,07,484)
2. **Loyal customers have highest AOV** — 17 Loyal customers average ₹89,758 spend each
3. **At-Risk pool needs attention** — 38 customers at risk contribute only 5.4% revenue; win-back campaigns recommended
4. **Offline slightly ahead** — 52.8% revenue offline vs 47.2% online; opportunity to grow digital channel
5. **Revenue peak in Jan 2026** — Monthly trend shows a spike in Jan 2026, likely driven by festive/seasonal demand
6. **Bargain Seekers are few but active** — Only 8 customers, avg spend ₹23,041 — nurture with targeted offers

---

## 📝 Resume-Ready Project Descriptions

**One-liner:**
> Built an Advanced Excel Market Research & Customer Segmentation Tool using RFM Analysis, demographic segmentation, and an interactive KPI dashboard to guide data-driven marketing strategy.

**ATS-Friendly Version:**
> Designed a Market Research & Customer Segmentation Tool in Microsoft Excel using RFM scoring (Recency, Frequency, Monetary), demographic grouping, and survey satisfaction analysis. Applied IFS-based segmentation logic to classify 200 customers into Loyal, High Value, At-Risk, Bargain Seeker, and General groups across 1,044 transactions (₹1 Cr+ revenue). Built an interactive dashboard with PivotTables, slicers, timeline filter, and KPI cards enabling actionable insights for targeted marketing campaigns.

---

## 👤 Author

**Atishey Jain**  
MBA Student | IMI Delhi  
🔗 [GitHub](https://github.com/atishey4) | [LinkedIn](https://www.linkedin.com/in/atishey-jain-66430715b/)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

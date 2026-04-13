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

### Dashboard Overview
![Dashboard Overview](screenshots/dashboard_overview.png)

### Customer Segmentation & KPI Cards
![Segmentation KPIs](screenshots/segmentation_kpis.png)

### RFM Analysis & Segment Distribution
![RFM Analysis](screenshots/rfm_analysis.png)

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
│   ├── dashboard_overview.png
│   ├── segmentation_kpis.png
│   └── rfm_analysis.png
│
├── LICENSE
└── README.md
```

---

## 📊 Dataset Description

The dataset contains realistic customer records across demographics, transactions, and survey responses.

### Customers Table (`tblCustomers`)
| Column | Description |
|--------|-------------|
| Customer ID | Unique identifier |
| Name | Customer full name |
| Gender | Male / Female |
| Age | Customer age |
| Region | North / South / East / West / Central |
| Income Range | Annual income bracket |
| Join Date | Customer acquisition date |

### Transactions Table (`tblTransactions`)
| Column | Description |
|--------|-------------|
| Transaction ID | Unique transaction reference |
| Customer ID | Linked customer |
| Date | Purchase date |
| Product Category | Electronics / FMCG / Apparel / Furniture / Software |
| Amount | Transaction value |

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

- ✅ **Total Customers** — Total unique customer count
- ✅ **Active Customers** — Customers with purchases in last 90 days
- ✅ **Average Order Value (AOV)** — Mean transaction value
- ✅ **Total Revenue** — Aggregate spend across all customers
- ✅ **Loyal Customers %** — Share of RFM 555 customers
- ✅ **At-Risk Customers %** — High recency + low frequency customers
- ✅ **Repeat Customer %** — Returning vs new customer ratio
- ✅ **Segment-wise Revenue** — Revenue breakdown by Loyal / At-Risk / Bargain Seeker / General
- ✅ **Avg Satisfaction Index** — Composite score from survey data
- ✅ **Channel Preference Split** — Online vs Offline distribution

---

## 📊 Dashboard Features

### Layout
```
┌────────────────────────────────────────────────────────┐
│  KPI Cards: Customers | AOV | Revenue | Loyal% | At-Risk%  │
├──────────────────────────┬─────────────────────────────┤
│  Bar Chart               │  Line Chart                 │
│  (Customers by AgeGroup) │  (Monthly Revenue Trend)    │
├──────────────────────────┼─────────────────────────────┤
│  Column Chart            │  Pie / Donut Chart          │
│  (Revenue by Segment)    │  (Segment Distribution)     │
├──────────────────────────┴─────────────────────────────┤
│  Satisfaction Heatmap: Region × Channel                  │
├────────────────────────────────────────────────────────┤
│  Slicers: Segment | Region | AgeGroup | Channel          │
└────────────────────────────────────────────────────────┘
```

### Visuals Included
- 📊 **Bar Chart** — Customers by Age Group and Income Bracket
- 📉 **Line Chart** — Monthly Revenue Trend by Segment
- 📊 **Column Chart** — Revenue by Customer Segment
- 🍩 **Pie / Donut Chart** — Segment Distribution (Loyal / At-Risk / Bargain Seeker / General)
- 🌡️ **Heatmap Table** — Satisfaction Index by Region × Channel
- 🎛️ **Slicers** — Segment, Region, AgeGroup, Channel
- 📅 **Timeline Filter** — Dynamic date-range filtering
- 🚨 **Conditional Formatting** — High-value customer highlights

---

## 💡 Business Insights Derived

1. **Loyal Segment** — Highest AOV and repeat rate; focus retention campaigns and exclusive offers
2. **At-Risk Customers** — High recency gap signals churn risk; trigger win-back email campaigns
3. **Bargain Seekers** — Frequent but low-spend; ideal for discount-driven promotions
4. **Regional Performance** — Pivot heatmap reveals which regions have highest satisfaction and spend
5. **Channel Preference** — Online channel dominates in younger age groups; offline preferred by 55+
6. **Segmentation ROI** — Targeted marketing to Loyal + High-Value segments can improve campaign ROI by 30–50%

---

## 📝 Resume-Ready Project Descriptions

**One-liner:**
> Built an Advanced Excel Market Research & Customer Segmentation Tool using RFM Analysis, demographic segmentation, and an interactive KPI dashboard to guide data-driven marketing strategy.

**ATS-Friendly Version:**
> Designed a Market Research & Customer Segmentation Tool in Microsoft Excel using RFM scoring (Recency, Frequency, Monetary), demographic grouping, and survey satisfaction analysis. Applied IFS-based segmentation logic to classify customers into Loyal, At-Risk, Bargain Seeker, and General groups. Built an interactive dashboard with PivotTables, slicers, and KPI cards enabling actionable insights for targeted marketing campaigns.

---

## 👤 Author

**Atishey Jain**  
MBA Student | IMI Delhi  
🔗 [GitHub](https://github.com/atishey4) | [LinkedIn](https://www.linkedin.com/in/atishey-jain-66430715b/)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).

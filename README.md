# 📱 Mobile Sales Dashboard — Power BI

> An end-to-end Business Intelligence project built in Power BI Desktop using DAX, Star Schema data modelling, and interactive visualisations across 3 report pages.

---

## 🧩 Problem Statement

Mobile retailers in India generate thousands of transactions every day across multiple cities, brands, models, and payment channels. Without a structured analytical system, business leaders cannot:

- Track which cities, brands, or phone models are generating the most revenue
- Monitor Month-To-Date (MTD) sales performance in real time
- Compare current period sales against the **Same Period Last Year (SPLY)**
- Identify seasonal trends, weekday patterns, or customer rating distributions
- Make data-driven decisions on pricing, restocking, and promotions

---

## ✅ Solution

An interactive **3-page Power BI dashboard** that transforms raw sales records into clear, actionable business insights — with dynamic slicers for Mobile Model, Payment Method, Brand, and Date.

---

## 📊 Dashboard Pages

### Page 1 — Main Dashboard

![Main Dashboard](screenshots/dashboard_main.png)

**KPI Cards:**

| Metric | Value |
|--------|-------|
| Total Sales | ₹769M |
| Total Quantity | 19K units |
| Total Transactions | 3,835 |
| Average Price | ₹40.11K |

**Visuals included:**
- 🗺️ Total Sales by City — bubble map across 18 Indian cities (Delhi & Mumbai lead)
- 📈 Total Quantity by Month — line chart showing seasonal trends (March peak: 1,700 units)
- ⭐ Ratings by Rating Status — Good ratings dominate at 100% index
- 🥧 Transactions by Payment Method — UPI 26.36% | Debit 24.72% | Credit 24.69% | Cash 24.22%
- 📊 Total Sales by Mobile Model — iPhone SE leads at ₹60M, OnePlus Nord ₹58M, Galaxy Note 20 ₹56M
- 📅 Total Sales by Day Name — Monday & Friday highest at ₹26.4M each
- 🏷️ Brand Summary Table — Apple ₹161M | Samsung ₹160M | OnePlus ₹153M | Vivo ₹150M | Xiaomi ₹143M

---

### Page 2 — MTD Report

![MTD Report](screenshots/dashboard_mtd.png)

Cumulative **Month-To-Date** daily sales trend powered by the `TOTALMTD()` DAX function.

- Filterable by Mobile Model, Payment Method, and Year / Quarter / Month / Day
- Example (August 2022): starts at ₹0.5M on Day 1, reaches ₹23.1M by end of month
- KPIs adjust dynamically to the selected period

---

### Page 3 — Same Period Last Year (SPLY)

![SPLY Comparison](screenshots/dashboard_sply.png)

Year-over-year comparison powered by `SAMEPERIODLASTYEAR()` DAX.

| Quarter | 2023 Sales | Prior Year | Change |
|---------|-----------|------------|--------|
| Qtr 1 | ₹62,889,301 | ₹66,946,186 | -6.1% 🔴 |
| Qtr 2 | ₹64,392,563 | ₹63,949,060 | +0.7% 🟢 |
| Qtr 3 | ₹62,957,202 | ₹66,594,369 | -5.5% 🔴 |
| Qtr 4 | ₹63,075,154 | ₹64,500,226 | -2.2% 🔴 |
| **Total** | **₹253,314,219** | **₹261,989,840** | **-3.3% 🔴** |

---

## ⚙️ DAX Queries Used

![DAX Query Editor](screenshots/dax_query1.png)

| Query | DAX Function | Purpose |
|-------|-------------|---------|
| Query 1 | `TOPN` | Top 10 raw data preview ordered by Transaction ID |
| Query 2 | `SELECTCOLUMNS` | Customer lookup ordered by Units Sold descending |
| Query 3 | `UNION` + `ROW` | 411-row statistical summary (count, mean, min, max, std dev, P25, P75) |
| Query 4 | `SUMMARIZECOLUMNS` | Core KPIs — Total Sales, Quantity, Transactions, Avg Price, MTD, SPLY |

---

## 🗄️ Data Model

**Star Schema** with two tables:

| Table | Type | Description |
|-------|------|-------------|
| `Sales_Data` | Fact table | All transaction records — revenue, quantity, ratings, payment, city, model |
| `Custom_Calendar` | Dimension table | Date table enabling all time intelligence DAX functions |

**Relationship:** `Custom_Calendar[Date]` → `Sales_Data[Date]` (One-to-Many)

---

## 💡 Key Business Insights

- 🏆 **Apple leads** brand revenue at ₹161M, just ahead of Samsung at ₹160M — a near dead-heat duopoly
- 📱 **iPhone SE** is the top-selling model at ₹60M
- 💳 **UPI** is the most preferred payment method (26.36%), reflecting India's digital payments growth
- 📅 **March** is the peak volume month — 1,700 units sold
- 📆 **Monday & Friday** are the highest revenue days at ₹26.4M each
- 📉 **2023 sales declined 3.3% YoY** (₹253M vs ₹262M prior year) — 3 of 4 quarters in decline

---

## 🛠️ Tools & Techniques

| Area | Detail |
|------|--------|
| Tool | Power BI Desktop |
| Query Language | DAX |
| Data Model | Star Schema |
| DAX Functions Used | `TOTALMTD`, `SAMEPERIODLASTYEAR`, `SUMMARIZECOLUMNS`, `SELECTCOLUMNS`, `UNION`, `ROW`, `TOPN` |
| Visuals | Bubble Map, Line Chart, Bar Chart, Pie Chart, Table, Funnel |
| Filters / Slicers | Mobile Model, Payment Method, Brand, Year-Quarter-Month-Day |

---

## 📂 Repository Structure

```
mobile-sales-dashboard-powerbi/
│
├── MS_Dashboard.pbix            ← Power BI project file (open in Power BI Desktop)
├── README.md                    ← This file
│
└── screenshots/
    ├── dashboard_main.png       ← Page 1: Main Dashboard
    ├── dashboard_mtd.png        ← Page 2: MTD Report
    ├── dashboard_sply.png       ← Page 3: Same Period Last Year
    ├── dax_query1.png           ← DAX Query 1 (TOPN raw preview)
    ├── dax_query2.png           ← DAX Query 2 (Customer lookup)
    ├── dax_query3.png           ← DAX Query 3 (Statistical summary)
    └── dax_query4.png           ← DAX Query 4 (Core KPI measures)
```

---

## 🚀 How to Run This Project

1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) — it is free
2. Clone or download this repository as a ZIP file
3. Open `MS_Dashboard.pbix` in Power BI Desktop
4. Use the slicers on each page to filter by Brand, Mobile Model, Payment Method, or Date

---

## 👤 Author

**HARSH**
Aspiring Data Analyst | Power BI | DAX | SQL | Excel
📧 harshrao4122001@gmail.com
🔗 [LinkedIn](www.linkedin.com/in/harsh-yadav-ab51a3249)
🐙 [GitHub](https://github.com/Harshrao52)

---

*Built as a portfolio project to demonstrate end-to-end Power BI development — from raw data and DAX modelling to interactive dashboard design and business insight generation.*

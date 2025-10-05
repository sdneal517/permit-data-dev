# 🏗️ North Canton Permit Data Dashboard

Public data → business insights.  
All building permits filed with the **City of North Canton** from **Jan 2024 – Sept 2025**, transformed and visualized in **Power BI**.

---

## 📊 Dashboard Pages
1. **Overview KPIs** – Total permits, total valuation, and unique contractors.
2. **Contractor Insights** – Rankings and trends showing who’s winning the most permits.
3. **Permit Type Trends** – Monthly activity and valuation by permit category.
4. **Map View** – Geographic focus on a selected permit type for top-value addresses.

Each page is designed to help business owners see where activity is rising, who’s leading, and where opportunities exist.

---

## ⚙️ Data Pipeline
| Layer | Purpose |
|-------|----------|
| **Bronze** | Raw exports from North Canton’s public permit portal |
| **Silver** | Cleaned and standardized tables |
| **Gold** | Final analysis view feeding Power BI |

**Core DAX Measures**
- `Total Permits = COUNTROWS(permits_gold)`
- `Total Valuation = SUM(permits_gold[valuation])`
- `Unique Contractors = DISTINCTCOUNT(permits_gold[contractor])`
- `Rank Contractors = RANKX(ALL(Contractor), [Total Permits])`

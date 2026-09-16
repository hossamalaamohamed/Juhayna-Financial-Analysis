# Juhayna Financial Intelligence & Predictive Analytics

An end-to-end **Power BI** solution that turns Juhayna's published financial statements into a CFO-level decision tool: profitability, liquidity, leverage and cash-conversion efficiency in one interactive model.

**Coverage period:** 2022 – Q2 2026 · **Granularity:** Year / Quarter

---

## Overview

The report answers the four questions a CFO asks every quarter:

1. **Are we growing, and is that growth profitable?** — revenue, gross and net margins, YoY movement.
2. **Can we meet our short-term obligations?** — current, quick and cash ratios.
3. **How leveraged are we, and can earnings service the debt?** — debt/equity, debt/EBIT, interest coverage.
4. **How fast does cash come back into the business?** — DSO, DIO, DPO and the cash conversion cycle.

Instead of a flat set of charts, each page pairs headline KPI cards with trend lines and diagnostic breakdowns, so a number that moves can be traced to the driver behind it.

---

## Dashboard Pages

| Page | Focus | What it shows |
|---|---|---|
| **Overview** | `JUHAYNA CFO DASHBOARD` | Executive summary — growth & profit, cash position, liquidity and leverage at a glance |
| **Performance** | `REVENUE – PROFITABILITY – COST STRUCTURE` | Revenue and EBIT trends, gross/EBIT/net margins, profitability ratios, cost structure |
| **Liquidity** | `SHORT-TERM LIQUIDITY & LEVERAGE` | Current / quick / cash ratios, debt ratios, interest coverage, solvency view |
| **Working Capital** | `DIO – DSO – DPO – CCC` | Cash conversion cycle with receivables and inventory trends |

Navigation is handled with bookmarks and action buttons, and every page shares a synced Year/Quarter slicer pane.

---

## KPIs & Measures

**Profitability & growth**
`Revenue` · `Revenue YoY %` · `Gross Profit` · `Gross Margin %` · `EBIT` · `EBIT Margin` · `EBT` · `PBT YoY %` · `Net Profit` · `Net Profit Margin` · `ROE` · `COGS`

**Liquidity**
`Current Ratio` · `Quick Ratio` · `Cash Ratio` · `Cash` · `Current Assets` · `Current_Liabilities`

**Leverage & solvency**
`Debt to Equity` · `Debt to EBIT` · `Net Debt to EBIT` · `EBIT to Interest (Interest Coverage)`

**Working capital & cash flow**
`DSO` · `DIO` · `DPO` · `CCC` · `Accounts Receivable` · `Inventory` · `Operating Cash Flow (CFO)`

---

## Data Model

* **Star schema** built on a dedicated `Dim_Date` calendar table marked as the date table, driving all time intelligence (YoY, quarter-over-quarter, running trends).
* **Dedicated measure tables** keep DAX separated from the fact tables and organised by owner/domain, so measures stay discoverable as the model grows.
* Financial statement facts (income statement, balance sheet, cash flow) are loaded and shaped in **Power Query**, then reduced to the columns the measures actually need.

---

## Tech Stack

* **Power BI Desktop** — data modelling and report authoring
* **DAX** — all KPIs, ratios and time-intelligence logic
* **Power Query (M)** — extraction, cleaning and shaping of the financial statements
* **Bookmarks, buttons & field parameters** — navigation and interactivity

---

## Repository Structure

```
.
├── modified.pbix        # Power BI report + data model
├── data/                # Source financial statements
├── docs/                # Screenshots and documentation
└── README.md
```

---

## Getting Started

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (latest version).
2. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   ```
3. Open `modified.pbix`.
4. If prompted, point the queries to the local `data/` folder and hit **Refresh**.

---

## Roadmap

* Forecasting for revenue, EBIT and cash position (Power BI analytics forecast / ARIMA in Python or R)
* Scenario and what-if analysis on margin and working-capital assumptions
* Anomaly detection on cost lines
* Automated refresh and publishing to the Power BI Service

---

## Disclaimer

Built for educational and analytical purposes using publicly available financial statements. Not affiliated with or endorsed by Juhayna Food Industries, and not investment advice.

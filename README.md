# retail-kpi-dashboard
Power BI Retail KPI Dashboard — Revenue vs Plan, Plan vs Actual, and Category Performance built on a star schema with clean DAX measures.

# Retail KPI Dashboard (Power BI)

Interactive Power BI report for a retail dataset with three pages:
- **Revenue vs Plan** – KPIs (Net Revenue, Gross Profit, GM%, Orders, AOV, Return Rate %) + category & month views  
- **Plan vs Actual** – Waterfall + variance breakdown + Region × Channel matrix  
- **Category Performance** – Top categories by Net Revenue with slicers (YearMonth, Region, Channel)

## Data Model
Star schema:
`FactOrder`, `FactOrderLine`, `FactPlan`, `FactReturn`
→ dimensions: `DimDate`, `DimRegion`, `DimChannel`, `DimCustomer`, `DimProduct`.

## Highlights
- Clean measure tables (KPI Core, Plan vs Actual, Titles & Flags)
- Dynamic titles (Selected Period/Region/Channel)
- Conditional formatting for variance
- Drill-through ready (kept off by default)

## Files
- `/report/Retail-KPI-Dashboard.pbix` – main report
- `/assets/` – screenshots for the README
- `/data/` (optional) – sample CSVs
- `.gitattributes` – Git LFS for large files

## How to Open
1. Clone repo, enable Git LFS (see below)
2. Open `report/Retail-KPI-Dashboard.pbix` in Power BI Desktop

## Publish
File → Publish → My workspace (or a target workspace).  
If you use a free trial, viewers need a Pro license or the report must be in a Premium workspace.

## License
MIT (see `LICENSE`).


# Retail KPI Dashboard (Power BI)

Interactive Power BI report for a retail dataset with three pages:
- **Revenue vs Plan** – KPIs (Net Revenue, Gross Profit, GM%, Orders, AOV, Return Rate %) + category & month views  
- **Plan vs Actual** – Waterfall + variance breakdown + Region × Channel matrix  
- **Category Performance** – Top categories by Net Revenue with slicers (YearMonth, Region, Channel)

## Data Model
Star schema:
Facts: `FactOrder`, `FactOrderLine`, `FactPlan`, `FactReturn`  
Dims: `DimDate`, `DimRegion`, `DimChannel`, `DimCustomer`, `DimProduct`

## Highlights
- Clean measures (KPI Core, Plan vs Actual, Titles & Flags)
- Dynamic titles (Selected Period / Region / Channel)
- Conditional formatting for variance
- Drill-through ready (kept off by default)

## Files
- `report/Retail KPI Dashboard.pbix` – main report
- `assets/` – screenshots for the README
- `data/` – sample CSVs (optional for demo or rebuild)
- `.gitattributes` – enables Git LFS for large files

## Open
1) Clone the repo  
2) (One-time) enable LFS:  
   ```bash
   git lfs install
   git lfs pull

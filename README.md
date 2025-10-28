# Retail KPI Dashboard — Revenue, Profit & Plan vs Actual

**Goal**: Executive Power BI dashboard with star schema, validated DAX KPIs, FYTD/R12M trends, and plan variance.

## Folder Setup
- Put the data CSV folder next to this kit: `ecom_powerbi_data/` containing 9 files (DimDate/DimProduct/DimCustomer/DimChannel/DimRegion/FactOrder/FactOrderLine/FactReturn/FactPlan).

## Steps
1. Open **Power BI Desktop** → *Get Data* → *Text/CSV* and import all 9 CSVs.
2. Mark `DimDate[Date]` as **Date table**.
3. Create a table named `_Measures` (Home → Enter Data, 1 dummy column → hide it). Paste `measures.dax` into this table.
4. Relationships (single direction, Dim → Fact):
   - `DimDate[DateKey]` → `FactOrder[order_date_key]`, `FactReturn[return_date_key]`, `FactPlan[date_key]`
   - `DimProduct[product_id]` → `FactOrderLine[product_id]`
   - `DimCustomer[customer_id]` → `FactOrder[customer_id]`
   - `DimChannel[channel_id]` → `FactOrder[channel_id]`, `FactPlan[channel_id]`
   - `DimRegion[region_id]` → `FactOrder[region_id]`, `FactPlan[region_id]`
5. Apply the theme: **View → Browse for themes → `theme.json`**.
6. Build pages:
   - **Page 1: Executive** — cards (6), combo chart by `YearMonth`, Region×Channel matrix with `[Rev Variance %]` color rules, slicers (Date/Region/Channel), title `[Title KPI Summary]`.
   - **Page 2: Category/Product** — bars for Category/Brand/SKU, detail table with GM% & Return Rate%.
   - **Page 3: Region & Channel** — map, channel small multiples, Region×Channel matrix (GP Variance %).
   - **Page 4: Returns** — Return Amt vs Revenue trend, Return Reason bar, Revenue→Discount→COGS→Returns→GP cards.
   - **Page 5: Plan vs Actual** — Actual vs Plan by month, variance line, Region×Channel heatmap.
7. Validation page — table by `YearMonth`: Net Revenue, Gross Profit, Return Amt, Rev Variance % (reconcile ±0.1%).

## Notes
- Fiscal year starts in July (adjust in `[Revenue FYTD]` if needed).
- Format: set $ for revenue/profit; % for rates. Group measures with display folders.

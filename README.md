# Blinkit Sales Analytics Dashboard

An interactive Power BI dashboard analyzing retail sales performance across item categories, outlet formats, and city-level markets for a grocery/quick-commerce business. The dashboard surfaces business-relevant patterns — geographic revenue concentration, outlet-tier and outlet-size performance, and product mix trends — to support data-driven decisions on market expansion, store format standardization, and category management.

## Tech Stack
- **Power BI** — Power Query (data cleaning), DAX (calculated columns), interactive report design
- Visuals: KPI cards, map (bubble/geo), donut chart, clustered column charts, slicers
- Cross-filtering enabled across all visuals for interactive exploration

## Key Business Questions Explored
- Which cities and outlet tiers drive the most revenue, and where is growth under-tapped?
- What outlet size format performs best, and should expansion strategy standardize around it?
- How does product mix (fat content category) break down, and is there room to shift it?

## Repository Structure
```
blinkit-sales-analytics/
├── README.md
├── data/
│   └── blinkit_sales_data.csv     # cleaned dataset (8,523 rows)
├── dashboard/
│   └── Basic_blinkit_5.pbix       # full Power BI report
└── screenshots/
    └── dashboard_preview.png
```

## How to Open
1. Download `dashboard/Basic_blinkit_5.pbix`
2. Open in **Power BI Desktop** (free download from Microsoft)
3. All data is embedded in the file (Import mode) — no additional setup needed
4. The raw dataset is also available separately in `data/blinkit_sales_data.csv` for use outside Power BI (e.g. Python/SQL practice)

## Note on Data Quality
During analysis, several fields were found to be mislabeled at the source — a field named `Outlet_Type` actually contained city names, and the `Item_Fat_Content` field contained inconsistent category labels (`LF`, `low fat`, `Low Fat` all representing the same category; similarly for `Regular`/`reg`). Both issues were identified and corrected as part of this analysis. Outlet-format-level detail (e.g., store type/size category beyond what's shown) was not available in the original dataset. The `Item_Weight` column also contains some missing values, inherited from the source data.

## Key Insights

**1. Revenue is heavily concentrated in one city — a risk, not just a win.**
Mumbai alone accounts for ₹12.92M (69.48%) of total sales across all four cities. While this shows Mumbai as the strongest market, it also signals a concentration risk — a demand shock or competitor entry in Mumbai alone could sharply impact overall performance.
> *Recommendation: investigate what's driving underperformance in Chennai (1.98%) and Jaipur (9.96%) — pricing, assortment, or market maturity — before scaling further into Mumbai alone.*

**2. Tier 3 outlets outperform Tier 1 and Tier 2 despite being a smaller-market category.**
Tier 3 leads total sales by outlet location type, ahead of Tier 2 and Tier 1, suggesting lower competition or under-served demand in smaller markets.
> *Recommendation: prioritize Tier 3 expansion over further Tier 1 investment, where the market may already be saturated.*

**3. Medium-sized outlets are the clear "sweet spot" format.**
Medium outlets significantly outperform Small and High-size outlets.
> *Recommendation: standardize new outlet rollouts around the medium format rather than defaulting to larger footprints, which don't show proportionally higher returns.*

**4. Regular items outsell Low Fat items roughly 65/35 by MRP value.**
This is a meaningful gap in a grocery/quick-commerce context where health-conscious positioning is increasingly common.
> *Recommendation: test targeted promotion of Low Fat SKUs in high-performing cities (e.g., Mumbai) to see if the mix can be shifted profitably, rather than assuming demand is fixed.*

## Author
Aryan Patel
[LinkedIn] · [GitHub]

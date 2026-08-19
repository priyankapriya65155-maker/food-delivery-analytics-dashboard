# Food Delivery Executive Dashboard

An interactive analytics dashboard analyzing 15,000 food delivery orders — built for a CEO/CFO-level view of revenue, delivery operations, and service quality, with live filtering and data-backed insights.

**🔗 Live Demo:** https://priyankapriya65155-maker.github.io/food-delivery-analytics-dashboard/


---

## What this project does

- Cleans and enriches a 15,000-row food delivery order dataset using Python (pandas)
- Engineers business-ready fields: revenue proxy, delivery delay, customer age/distance bands, time-of-day buckets
- Surfaces 7 data-backed business insights — e.g., delayed deliveries drive a **4x higher refund rate** than on-time orders
- Renders a 12-chart interactive dashboard with live filters (city tier, premium status, festival/weekend, promo usage)
- Includes a full Power BI rebuild spec (DAX measures + layout wireframe) for enterprise deployment

## Key findings

| # | Finding |
|---|---|
| 1 | Delayed deliveries get refunded **~4x more often** than on-time orders (12.6% vs 3.2%) |
| 2 | Premium customers (28% of base) spend **12% more per order** |
| 3 | **60% of orders** sit exactly at the platform's ₹100 minimum order value |
| 4 | Tier 3 cities generate **~50% of revenue** on order volume, not higher spend per order |
| 5 | Promo code usage shows **no measurable lift** in average order value — flagged for an ROI audit |
| 6 | Traffic, weather, distance, and delivery-partner experience show **near-zero correlation** with delays — root cause isn't captured in current data |
| 7 | Festival/weekend orders carry an **8% revenue lift** with no cancellation trade-off |

## Tech stack

- **Python** (pandas, numpy) — data cleaning, feature engineering, statistical analysis
- **HTML / JavaScript / Chart.js** — standalone interactive dashboard (this repo's live demo)
- **React / Recharts** — component version of the same dashboard
- **Power BI** — DAX measures and dashboard layout spec for enterprise rebuild

## Project structure

```
├── index.html                            # interactive dashboard (this is the live demo)
├── food_delivery_analytics_cleaned.csv   # raw source data
├── prepare_dashboard_data.py             # Python data cleaning + feature engineering
├── food_delivery_powerbi_ready.csv       # cleaned, enriched output dataset
├── powerbi_dax_and_layout.md             # DAX measures spec + Power BI layout wireframe
├── food_delivery_dashboard_preview.jsx   # React/Recharts component version
└── food_delivery_dashboard_snapshot.png  # preview image (shown above)
```

## How to run it locally

**Interactive dashboard (no setup):**
Just open `index.html` in any browser.

**Data pipeline:**
```bash
pip install pandas numpy
python prepare_dashboard_data.py
```
This regenerates `food_delivery_powerbi_ready.csv` from the raw dataset.

**Power BI version:**
Import `food_delivery_powerbi_ready.csv` into Power BI Desktop and follow the measures and layout in `powerbi_dax_and_layout.md`.

## Notes on data assumptions

- The dataset has no true cost/COGS column, so **"Net Revenue" is a proxy** (final amount paid − discount), not audited profit.
- There's no continuous calendar date field in the source data (only month + day-of-week), so the monthly trend chart uses a modeled date and should be read as illustrative, not exact historical sequence.

## License

This project uses a synthetic/sample dataset for portfolio purposes.

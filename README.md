# Swish 10-Min Delivery — Bangalore Zone Operations Dashboard

An end-to-end **Advanced Excel operations dashboard** built for a hypothetical 10-minute food
delivery service, modeled on real quick-commerce operations (order lifecycle, kitchen prep,
rider logistics, inventory, and customer complaints across 10 Bangalore zones).

The workbook simulates a live ops control center: a single raw order log feeds every other
sheet automatically, so the whole dashboard recalculates the moment new orders are logged —
no manual copy-pasting, no static numbers.

*(Full PDF snapshot: `Swish_Executive_Dashboard.pdf`)*

## What this demonstrates

This project was built to showcase practical, job-ready Excel skills for a **Data Analyst /
Business Operations** role — specifically the kind of real-time reporting and data validation
work used in live-ops and command-center environments.

| Skill | Where it's used |
|---|---|
| **Lookup formulas** — `VLOOKUP`, `INDEX`/`MATCH` | Rider names pulled into the Attendance sheet; kitchen peak-load pulled into the Ops tracker |
| **Multi-condition aggregation** — `COUNTIFS`, `SUMIFS`, `AVERAGEIFS` | Every rollup sheet (Zone Performance, Kitchen Ops, Executive Dashboard KPIs) aggregates the raw order log live |
| **Error-safe formulas** — `IFERROR` | Wraps every ratio/average so a zero-order zone shows `0`, not `#DIV/0!` |
| **Nested logic** — `IF`, `AND` | Delay flags, delivery-time calculations, and restock alerts |
| **Dynamic date-driven reporting** | `Report Date` auto-pulls `=MAX(...)` from the order log, and every KPI card recalculates off that date |
| **Helper columns / calculation layer** | Hidden `calc` columns (Prep Minutes, Order Hour, Delay Flag) keep raw data clean while powering every chart and KPI |
| **Conditional formatting** | Data bars on order volume, color scales on cancellation rate and kitchen heatmaps, red/green flags on inventory restock status |
| **Native Excel charts** | Line chart (hourly order trend) and bar chart (zone-wise revenue) embedded directly in the dashboard, sourced from helper tables |
| **Cross-sheet architecture** | 11 linked sheets acting like a mini relational model — one fact table (Daily Order Tracker) driving 8 downstream reports |
| **Editable assumptions box** | Rider earnings re-price instantly by editing one blue input cell (`Base Rate / Delivery`) |

## Workbook structure

- **Executive Dashboard** — KPI cards (orders, deliveries, revenue, on-time %), zone-wise
  performance table, kitchen load heatmap, hourly order trend chart, zone revenue chart.
- **Daily Order Tracker** — the single source of truth: one row per order, with hidden
  calculation columns (prep time, order hour, delay flag) that power everything downstream.
- **Hourly_Helper** — pivots the order log into an hour-by-hour load matrix per kitchen.
- **Kitchen Operations Tracker** — live prep-time, backlog, and efficiency % per kitchen.
- **Food Preparation Monitor** — item-level prep time vs. target, with an on-time/delayed flag.
- **Rider Performance Tracker** — deliveries, distance, earnings, and acceptance rate per
  rider, driven by an editable assumptions box.
- **Zone Performance** — revenue, delivery time, cancellation rate, and rating per zone.
- **Inventory Tracker** — live stock balance with automatic reorder alerts.
- **Rider Attendance** — shift log with `VLOOKUP`-driven rider names and attendance status.
- **Customer Complaints** / **Cancellation & Refund Tracker** — issue logs feeding the
  dashboard's open-complaints KPI.

## Notes

- All figures are synthetic/sample data generated for demonstration purposes — this does not
  represent a real company's operations.
- Built and verified in Excel; every KPI is a live formula (no hardcoded results), so changing
  the underlying order log recalculates the entire dashboard.

## Files in this repo

- `Swish_10Min_Delivery_Ops_Dashboard.xlsx` — the workbook.
- `Swish_Executive_Dashboard.pdf` — a PDF snapshot of the Executive Dashboard tab.

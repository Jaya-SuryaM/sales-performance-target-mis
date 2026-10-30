# Sales Performance & Target MIS

An Excel dashboard for comparing sales revenue with monthly targets across regions, products, and salespeople.

![Sales dashboard preview](dashboard_preview.png)

## Dashboard

The workbook opens with Year = 2026, Region = All, and Month = All. Use the blue dropdowns to change those filters. KPI cards, achievement, salesperson, product, and daily views follow the selected filters. The region chart compares all four regions for the selected year and month, so it remains a useful comparison when one region is selected. Monthly revenue and delta charts show the whole year for the selected region. When Month is All, the daily chart shows the latest month with data.

The dashboard includes four KPI cards and seven charts:

- KPI cards: revenue, target, revenue delta, and sales records
- Target achievement percentage
- Monthly revenue compared with target
- Monthly revenue delta
- Achievement by region
- Revenue and target by salesperson
- Top eight products by revenue
- Daily revenue for the selected month, or the latest month when Month is set to All

## Workbook tabs

| Tab | Contents |
| --- | --- |
| Dashboard | Filterable KPI cards and charts |
| Sales Detail | 3,000 sales records with date, salesperson, region, product, quantity, and amount |
| Target Detail | 80 monthly target and actual records |
| Product Summary | Revenue and units by product |
| Monthly Trend | Monthly revenue and sales record totals |
| Daily Summary | Daily revenue, sales record totals, and units |
| Monthly Performance | Monthly revenue, target, delta, and achievement summary |
| Reference Data | Month, salesperson, and region lookup lists |
| Helper Tables | Supporting calculations used by the dashboard charts |

## Metrics and data

- **Revenue:** sum of sales amounts.
- **Target:** sum of target amounts.
- **Delta:** revenue minus target.
- **Achievement:** revenue divided by target.
- **Sales records:** count of matching rows in Sales Detail. The workbook has no order ID, so this is not a distinct order count.

The Daily Summary and Monthly Trend tabs use the heading `orders` for these row counts; interpret them as sales records, not unique orders.

The workbook uses rupee formatting. It contains 3,000 sales rows dated January 1 through October 30, 2026, and 80 monthly target rows. Salesperson names are anonymized as `Salesperson 01` through `Salesperson 08`; the sales and target figures are unchanged.

## Data source and refresh

Sales and target rows are embedded in the workbook in the `v_sales_detail` and `v_target_vs_actual` query tables and saved Data Model. The workbook does not record a separate source file or service URL. For a new data load, update the upstream tables or query feeding the Data Model while keeping the existing column names, then use **Data → Refresh All** in desktop Excel and check the totals before sharing the file.

The Year dropdown reads its options from `Reference Data!G2:G...`. Add each year supported by the workbook on the next row in that column, and make sure the refreshed sales and target data contain matching year values. The dropdown expands automatically. Update `dashboard_preview.png` whenever you change the workbook's data or default filters.

## Files

- [Excel workbook](projectbook1_completed.xlsx)
- [Dashboard preview](dashboard_preview.png)

# Saudi Supermarket Sales: Power BI Dashboard

Executive Power BI dashboard on a sample of Saudi supermarket transactions (48 rows, Jan–Jul 2025, SAR). One page: KPIs on top, trends in the middle, drivers below.

![Dashboard](docs/dashboard.png)

## Key numbers

| KPI | Value |
|---|---|
| Net Sales | SAR 1,530.17 |
| Avg Basket | SAR 31.88 |
| Discount Rate | 5.35% (amber) |
| Transactions | 48 |
| Loyalty Share | 48.9% |
| Digital Payment Share | 75.2% |

The Western region drives 56.6% of net sales. Discounts peaked in June at 19.1% of gross sales.

## What's inside

- **6 KPI cards** with status colors. Discount Rate is green up to 5%, amber from 5% to 8%, red above 8%, driven by one DAX measure.
- **32 DAX measures** grouped in display folders (Sales, Basket, Discounts, Time, Customers, Products, Formatting).
- **5 charts:** net sales by month, discount rate by month, net sales by product, by region and by payment method.
- **Full cross-filtering** across Region, City, Category and Customer Segment slicers, and between charts.
- **Dynamic insight lines** (top region, top product) that change with every filter.
- **Custom JSON theme** applied across all visuals.

## Repository layout

| Folder | Content |
|---|---|
| `dax/` | All DAX measures |
| `theme/` | Power BI theme (JSON) |
| `data/` | Sample dataset (xlsx) |
| `docs/` | Dashboard image, insights spec, LinkedIn carousel (PDF) |

## Data model

- `Saudi_Supermarket_Sales`: fact table, one row per transaction (48 rows).
- `Dim Date`: date table, related to the fact table on `Date` (many-to-one).

## How to rebuild it

1. Open Power BI Desktop and load `data/Saudi_Supermarket_Sales_SalesData.xlsx` (sheet `SalesData`).
2. Create `Dim Date` (CALENDAR over the data range) and relate it to the fact table on `Date`.
3. Open **DAX query view**, paste the contents of `dax/Saudi_Supermarket_Measures.dax`, and click **Update model with changes**.
4. Import the theme: **View → Themes → Browse for themes** and select `theme/Saudi_Supermarket_Theme_v2.json`.
5. Build the visuals: 6 cards (`Net Sales`, `Avg Basket`, `Discount Rate %`, `Transactions`, `Loyalty Share %`, `Digital Payment Share %`) and the five charts, then add the four slicers.
6. For the Discount Rate card: **Format → Callout value → Color → fx → Field value → `Discount Status Color`**.

## Business questions the dashboard answers

- Which region and products drive net sales?
- Is the discount level healthy, and when did it spike?
- How big is the loyalty segment, and how do its baskets compare?
- Which payment methods dominate?

## Limitations

The dataset is a small sample (48 transactions), so this is an exercise in modelling and dashboard design, not a market conclusion.


# Saudi Supermarket Sales: Power BI Dashboard

Executive Power BI dashboard on a sample of Saudi supermarket transactions (48 rows, Jan-Jul 2025, SAR).

## What's inside
- 6 KPI cards with status colors (Discount Rate: green up to 5%, amber 5-8%, red above 8%)
- 32 DAX measures grouped in display folders (`dax/`)
- Charts: monthly net sales, discount rate trend, net sales by product, region and payment method
- Full cross-filtering across Region, City, Category and Customer Segment slicers
- Dynamic insight lines driven by measures (Top Region / Top Product)
- Custom JSON theme (`theme/`), imported via Design > Import theme

## Key numbers
| KPI | Value |
|---|---|
| Net Sales | SAR 1,530.17 |
| Avg Basket | SAR 31.88 |
| Discount Rate | 5.35% |
| Transactions | 48 |
| Loyalty Share | 48.9% |
| Digital Payment Share | 75.2% |

Western region drives 56.6% of net sales.

## Layout
- `dax/` DAX measures
- `theme/` Power BI theme (JSON)
- `data/` sample dataset (xlsx)
- `docs/` insights spec and LinkedIn carousel (PDF)

## Data model
`Saudi_Supermarket_Sales` (fact) related to `Dim Date` on `Date`.

## Note
The dataset is a small sample, so this project is an exercise in modelling and dashboard design, not a market conclusion.

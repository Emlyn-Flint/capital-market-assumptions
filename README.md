# Long-Term Capital Market Assumptions

A collation of long-term asset class views published by global asset managers and consultants, compiled by Peresec.

This repository holds the data behind the Peresec *Long-Term Capital Market Assumptions 2026* summary: the 2024, 2025 and 2026 editions.

## What is in the data

Each edition collects the expected return, standard deviation and, from 2025, correlation views that institutions publish in their capital market assumption reports. Every institution's own asset classes are mapped to 36 standard asset names in four classes (Equities, Fixed Income, Cash, Alternative).

| Edition | Institutions | Return views | Standard deviation views | Correlation views |
|---|---|---|---|---|
| 2024 | 31 | 560 | 479 | none |
| 2025 | 40 | 708 | 548 | 6,420 |
| 2026 | 50 | 851 | 667 | 6,572 |

The intended basis for every return is a **10-year horizon in USD, as an annualised nominal geometric return**. Risk is the forecast annual standard deviation. Not every institution publishes on that basis: see `data/basis_by_institution.csv`.

### Currency convention

Returns are shown from the point of view of a USD investor:

- **Equities** are unhedged, in USD.
- **Bonds** are hedged to USD. Emerging-market local-currency debt is the exception and is unhedged.
- **Developed Markets Ex US Cash** is the local-currency cash rate, not a USD return.
- **Alternatives** are in USD as published.

Where a report gives its own USD figure on this convention, that figure is used. Where it gives only a local-currency or differently hedged figure, Peresec converted it by interest-rate parity: USD return = published return + (USD cash rate - local cash rate), applied to each country or regional component before averaging, using the cash rates in the same report. Reports with no usable cash rates are left as published and marked as such.

## Files

- `data/cma_2024_2026.csv`: the full dataset, one row per view.
  Columns: `edition`, `asset_class_1`, `asset_1`, `asset_class_2`, `asset_2`, `institution`, `statistic` (`Return`, `Standard Deviation` or `Correlation`), `forecast` (a decimal: 0.065 is 6.5%). `asset_class_2` and `asset_2` are filled only for correlations, which are stored in both directions with the diagonal.
- `data/basis_by_institution.csv`: for each institution and edition, the report title and date, horizon, currency, return basis, and where the views depart from the intended basis.
- `data/consensus_summary.csv`: for each edition, asset and statistic, the median, mean, number of views, range and middle half, and the change in the median on the prior edition.
- `data/consensus_correlation_core_2026.csv` and `..._2025.csv`: the consensus correlation matrix for the 11 core assets (the building blocks of a global balanced fund: US Large Cap, Developed Markets Ex US, Emerging Markets, US Government, US Inv. Grade Corporate, US High Yield, US TIPS, Emerging Markets Govt (Hard), US Cash, REITS and Commodities), adjusted to the nearest valid correlation matrix.
- `data/consensus_correlation_core_2026_unadjusted.csv` and `..._2025_unadjusted.csv`: the same matrices before adjustment.

## How to read the figures

- **Median as the headline.** The consensus for an asset is the median across the institutions that publish a view for it, so the number of views differs from asset to asset. Treat any figure resting on fewer than five views with care.
- **Changes between editions** in `consensus_summary.csv` are the difference between the two editions' medians, each taken over every institution with a view that year. Coverage grew from 31 to 40 to 50 institutions, so a change reflects both revised views and changes in which institutions contribute.
- **Basis.** Each institution is marked as one of the following in `basis_by_institution.csv`:
  - *on basis*: published on the intended basis.
  - *converted*: Peresec converted the report's figures to the intended basis: arithmetic to geometric (arithmetic less half the variance), real to nominal (real plus inflation), or to the currency convention above.
  - *basis not stated*: the report does not say whether its returns are geometric or arithmetic; the figures are used as they stand.
  - *as published*: the report uses another horizon or currency and offers no means of converting, so the figures are used as they stand.
- **Regional averages.** Some lines, mostly the "Developed Markets Ex US" assets, are simple averages of an institution's country or regional figures where it publishes no aggregate.
- **Zero standard deviations.** A few institutions report no volatility for cash, held as zero in the dataset. The consensus summary treats these as missing.
- **Consensus correlation matrix.** Each cell is the median over the institutions that publish that pair, so cells rest on different sets of institutions and the raw matrix is not a valid correlation matrix. The adjusted version is the nearest positive semi-definite matrix with a unit diagonal (Higham, 2002), rounded to four decimals. Every pair among the 11 core assets has at least five views. For this set the median matrix is already valid in both 2026 and 2025, so the adjusted and unadjusted files are identical; both are kept so the check is visible.
- **Names.** BNY Mellon was renamed BNY Investments in 2026 and appears as BNY Mellon throughout.

## Sources and checking

All figures are taken from publicly available reports; the reports themselves belong to their publishers and are not reproduced here. The 2024 to 2026 data was checked value by value against the source reports in November 2026. The Vanguard 2025 views (28 rows) could not be re-checked because the original page is no longer available.

## Scope

The data is a collation of third-party views, provided for information and research. It is not investment advice, and Peresec does not endorse any individual forecast.

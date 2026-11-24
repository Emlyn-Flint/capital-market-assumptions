# Changelog

## 2026 edition (November 2026)

- First release on GitHub, covering the 2024, 2025 and 2026 editions.
- All three editions were checked against the source reports before release. Compared with the figures Peresec circulated earlier:
  - 96 values corrected where the typed figure did not match the report, mostly correlations (Envestnet PMC 2025, JP Morgan 2026, BNY 2025 and 2026, Research Affiliates, Horizon, Verus, Nuveen, TDAM) and the Sellwood Consulting 2026 standard deviations.
  - Envestnet PMC 2024 returns converted from arithmetic to geometric, as already done for 2025.
  - HSBC 2025 and Ninety One 2024 to 2026 returns moved from local-currency to USD figures.
  - EFG 2026: rows that held Swiss assets under emerging-market names replaced or removed.
  - Returns put on one currency convention (equities unhedged in USD, bonds hedged to USD, ex-US cash as the local-currency rate): 111 return values across 10 institutions changed, either to the report's own USD figure or by interest-rate parity using the report's cash rates. Affected: Amundi, CI GAM, HSBC, High Level Wealth Management, Ninety One, Northern Trust, RBC GAM, Schroders, State Street and TDAM. Mackenzie, Candriam, Deutsche Bank and some State Street lines could not be converted and are left as published.
  - Return basis recorded as geometric for BlackRock (2024 to 2026) and Meketa (2026).
  - PGIM cash volatility removed (2024 to 2026): the reports print no figure and the earlier data held 0. Zero cash volatilities that are published (BlackRock, Schroders, EFG) are kept and counted in the consensus.
- The change on the prior edition in `consensus_summary.csv` is the difference between the two editions' all-institution medians.
- The core correlation matrices cover 11 assets: the building blocks of a global balanced fund. The 2025 matrix is valid as it stands; the 2026 matrix is adjusted slightly to the nearest valid matrix.

## Correction (24 November 2026)

- Inspire 2025: the correlation matrix was incomplete. 10 pairs were held in one direction only, and another 10 pairs and 5 unit diagonals were missing; all are added from the report, so the 7-asset matrix is now complete.
- `consensus_correlation_core_2025.csv`: each cell is now the median across institutions, counting each institution once per pair. Two cells change (Developed Markets Ex US with US Cash and with US Large Cap).
- `basis_by_institution.csv`: the State Street note wrongly said its cash was converted to USD; its non-US assets, including ex-US cash, are in local currency.
- The currency notes now state that only returns are converted; volatilities and correlations are as published.

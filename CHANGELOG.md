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
- The core correlation matrices cover 11 assets: the building blocks of a global balanced fund. Both are valid correlation matrices as they stand, so the separate adjusted and unadjusted files are replaced by one file per edition.

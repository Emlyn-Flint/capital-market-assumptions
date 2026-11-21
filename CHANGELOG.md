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
- Editions added for institutions present in some years but not others (1,194 rows across 24 institution-editions), each treated the same way as the institution's edition already held:
  - 2024: Atlanta Consulting, Capital Spectator, Cohen & Steers, High Level Wealth Management, Inspire, Janney, KKR, Lombard Odier, Nasdaq eVestment Research, NEPC, Nuveen, State Street, TDAM, Fidelity International, SEI.
  - 2025: Atlanta Consulting, Capital Spectator, ELM, KKR, Lombard Odier, NEPC, Fidelity International, Janus Henderson.
  - 2026: Envestnet PMC.
  - Points to note: Atlanta Consulting 2024 is taken from the comparison columns of its 2025 report; KKR's earlier figures are five-year forecasts; three Lombard Odier 2025 values and both NEPC decks come from copies hosted by third parties; TDAM and High Level Wealth Management are converted from a Canadian-dollar basis as in 2026; Fidelity International 2024 and Janus Henderson 2025 are taken from the comparison figures in a later report; SEI 2024 is the Canadian version of its report, in Canadian dollars, covering 5 of its 12 assets.
- The change on the prior edition in `consensus_summary.csv` is the difference between the two editions' all-institution medians.
- The core correlation matrices cover 11 assets: the building blocks of a global balanced fund. Both are valid correlation matrices as they stand, so the separate adjusted and unadjusted files are replaced by one file per edition.

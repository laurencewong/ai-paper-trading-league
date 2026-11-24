# Changelog

Corrections and rule-implementation changes are added here as new dated entries. Past records are never edited.

- **2026-11-24:** The setups position-size check now prices a stock setup at the price it would fill at (its trigger for buy-limit and buy-stop setups, the last price for at-open setups, plus slippage) instead of the prior close. This applies from the Tue 11/24 13:30 PT setup run (setups for Wed 11/25) on. The 10% position cap is unchanged. Setups committed earlier, and their rejections, stand as recorded.
- **2026-11-24:** A stock buy-limit setup whose order limit equals its trigger price now fills at the trigger plus slippage, the same as a buy-limit with no order limit. Before this, the fill rule (trigger plus slippage) always landed just above such a limit, so the setup could trigger but never fill. A fill is still never better than the trigger. An order limit above the trigger works as before, and one below the trigger is still refused. This applies to setups for Fri 11/27 on, so the first fill run it can affect is Fri 11/27 06:45 PT. Setups for earlier sessions, and their receipts, stand as recorded.

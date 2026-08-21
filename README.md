# Overnight vs Intraday Returns: Nifty 50

Decomposes 15 years of Nifty 50 daily returns (2010–2026, ~4,100 trading days)
into an overnight component (close → next open) and an intraday component
(open → close).

**Headline finding:** the entire equity premium — and more — accrued overnight.
Overnight returns averaged ~+26% annualised; intraday returns averaged ~−15%
annualised (both statistically significant, |t| > 4). ₹1 held overnight-only
since 2010 grew to ~₹60; held intraday-only, it fell below ₹1.

Robustness so far: stale open prints are negligible (12/4,082); all extreme
overnight moves map to real events (Covid crash, demonetisation night, 2024
election); the effect *strengthens* when the extreme 1% of days are removed.

**This is a fact about when returns accrue, not a tradeable strategy** — the
~10bps/night edge would be consumed by twice-daily transaction costs.

Work in progress: regime analysis, cost modelling, full writeup. Data: Yahoo
Finance via yfinance; free data caveats apply, especially for open prices.
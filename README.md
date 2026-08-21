# Overnight vs Intraday Returns: Nifty 50

Decomposes 15 years of Nifty 50 daily returns (2010–2026, ~4,100 trading days)
into an overnight component (close → next open) and an intraday component
(open → close). This effect is documented in US equities; this project tests
whether it holds in Indian data, and finds a stronger version (US intraday is
roughly flat; Nifty's is significantly negative).

**Headline finding:** the entire equity premium — and more — accrued overnight.
Overnight returns averaged ~+26% annualised; intraday returns averaged ~−15%
annualised (both statistically significant, |t| > 4). ₹1 held overnight-only
since 2010 grew to ~₹60; held intraday-only, it fell below ₹1.

Robustness: stale open prints are negligible (12/4,082), and all extreme
overnight moves map to real events (Covid crash, demonetisation night, 2024
election). Clipping the extreme 1% of nights raises the terminal value rather
than lowering it. Three five-year sub-periods show overnight annualised returns
positive and intraday negative throughout (+23.0/−14.2, +34.9/−21.5,
+21.1/−10.1), and periods in the top quartile of trailing volatility showed a
larger overnight premium (+34% vs +23%).

Transaction costs are estimated from a futures round trip priced on 20 August
2026: ~6 bps round trip → net ~4.3 bps/night → ~11% annualised → ~4.4% above the
risk-free rate, before slippage. The remaining excess is best read as
compensation for overnight crash risk rather than an exploitable anomaly.

Data: Yahoo Finance via yfinance; free data caveats apply, especially for open
prices.

Limitations are documented in the notebook — price index (excludes dividends),
i.i.d. assumptions imperfect given volatility clustering, costs priced on futures
while returns are measured on spot, and today's cost structure applied
retrospectively.

To run: `pip install yfinance pandas matplotlib scipy`, open `Returns.ipynb`,
Run All.
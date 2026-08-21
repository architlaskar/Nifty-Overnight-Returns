# Overnight vs Intraday Returns: Nifty 50

Decomposes 15 years of Nifty 50 daily returns (January 2010 – 20 August 2026,
4,085 trading days) into an overnight component (close → next open) and an
intraday component (open → close). This effect is documented in US equities;
this project tests whether it holds in Indian data, and finds a stronger version
(US intraday is roughly flat; Nifty's is significantly negative).

**Headline finding:** the entire equity premium — and more — accrued overnight.
Overnight returns averaged +26.0% annualised; intraday returns averaged −15.0%
annualised (t = 10.8 and −4.4). ₹1 held overnight-only since 2010 grew to ₹62.17;
held intraday-only, it fell to ₹0.07. Buy-and-hold returned ₹4.63.

Robustness: stale open prints are negligible (12/4,085), and all extreme
overnight moves map to real events (Covid crash, demonetisation night, 2024
election). Clipping the extreme 1% of nights raises the terminal value rather
than lowering it. Three five-year sub-periods show overnight annualised returns
positive and intraday negative throughout (+23.0/−14.2, +34.9/−21.5,
+21.2/−10.2), and periods in the top quartile of trailing volatility showed a
larger overnight premium (33.9% vs 23.3%).

Transaction costs are estimated from a futures round trip priced on 20 August
2026: ~6 bps round trip → net ~4.3 bps/night → ~11% annualised → ~4.5% above the
risk-free rate, before slippage. The remaining excess is best read as
compensation for overnight crash risk rather than an exploitable anomaly.

Data: Yahoo Finance via yfinance; free data caveats apply, especially for open
prices. The sample end date is pinned, so the notebook reproduces these figures
exactly.

Limitations are documented in the notebook — price index (excludes dividends),
i.i.d. assumptions imperfect given volatility clustering, costs priced on futures
while returns are measured on spot, and today's cost structure applied
retrospectively.

To run: `pip install yfinance pandas matplotlib scipy`, open `Returns.ipynb`,
Run All.
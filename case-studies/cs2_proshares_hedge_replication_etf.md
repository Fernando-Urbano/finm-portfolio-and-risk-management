# 2. Case Study: ProShares Hedge Replication ETF

## Introduction
ProShares has extensive research and development behind its lineup of exchange-traded funds (ETFs).

ProShares was a pioneer in packaging liquid alternative strategies into ETFs.

The presentation by Joanne Hill focused on "Hedge Fund Replication: A Closer Look," specifically on one of ProShares' liquid alternative strategy products: the Hedge Fund Replication ETF (HDG).

The Hedge Fund Replication ETF offered:
- Transparency
- Daily liquidity
- Low fees

However, the audience was resistant to the product, as most hedge funds had underperformed the overall stock market in recent years:
- HDG 2013 returns: 4.4% with volatility of 4.8%
- S&P 2013 returns: 32.4% with volatility of 11%

## ProShares
A leader in ETFs for shorting and leveraging positions, ProShares allowed investors to take hedging and speculative positions without directly using derivatives.

During the 2008 financial crisis, challenges arose due to the fact that most ETFs reset daily. With high volatility and market stress, long-term investors saw returns deviate from the expected multiple of index returns over periods longer than a day, leading to problems and lawsuits.

When market volatility normalized, ETFs regained popularity.

From 2010 onwards, ProShares focused on creating alternative strategies. By the end of 2013, ProShares managed over $33 billion in assets and more than 140 ETFs. Their offerings spanned Global Fixed Income, Hedge Strategies, Geared, and Inflation & Volatility categories.

## ProShares Hedge Replication ETF (HDG)
The primary objective of the Hedge Replication ETF was to give investors with a sizable portfolio exposure to hedge fund investments, as part of an allocation to alternatives, in order to improve risk-adjusted returns.

Key arguments included:
- Adjusting a 60-40 portfolio (60% stocks and 40% bonds) by reallocating 20% of equity exposure into hedge funds could maintain the same average returns while decreasing hypothetical risk.
- Investing $10,000 in hedge funds from 1994 to 2013 would have yielded a 10% higher return than stocks, and more than double the return of bonds.
- Hedge funds provided a smoother ride than stocks in the past five years, though stocks ultimately performed better.

### HRFI (Hedge Fund Research Index)
The HRFI replicates hedge fund performance and offers:
- Less than half the volatility of the S&P.
- Annualized returns less than 1% lower than the S&P.
- Half the drawdown of equities during the 2008 crisis.

Investing in individual hedge funds was beneficial if the investor was willing to invest time in finding quality funds and had the patience to wait before withdrawing money.

### Disadvantages of the Hedge Fund Market
The hedge fund market had several drawbacks:
- Most hedge funds required substantial minimum investments, making them accessible only to large institutions and wealthy investors.
- Many hedge funds had restrictive terms and notice periods regarding withdrawals.
- Hedge funds often lacked transparency, as their strategies were largely proprietary.
- Fees were significant: typically 2% annually, plus a 20% performance fee.
- Hedge fund taxation often involved K-1 forms, complicating tax filings for some investors.

### HDG and Replication
HDG aimed to achieve a high correlation with hedge fund beta by tracking the Merrill Lynch Factor Model, which targeted a strong correlation to the HRFI.

HDG sought to replicate the performance of the Merrill Lynch Factor Model.

## Merrill Lynch Factor Model for Tracking HRFI
Merrill Lynch developed an index to replicate hedge fund performance without direct investment in hedge funds, aiming to mimic the HRFI.

HRFI is the broadest index from Hedge Fund Research Inc., a global leader in the alternative investment industry.

To replicate hedge fund risk and returns without directly investing, the model used regression analysis to assign weights to market factors that contributed to hedge fund performance.

The original Merrill Lynch Factor Model included six factors:
- S&P 500
- Russell 2000
- MSCI EAFE (Developed Stock Markets)
- MSCI Emerging Markets
- Eurodollar/U.S. Dollar exchange rate
- Three-month Eurodollar Deposit Yields

The model used a rolling regression of the previous 24 months of returns and allowed weights on the six factors, imposing certain constraints.

However, some components of the index were unavailable in the market. To create a benchmark for HDG, adjustments were made:
- MLFM-ES replaced the Three-month Eurodollar Deposit Yields.
- UltraShort Euro (EUO) replaced the Eurodollar/U.S. Dollar exchange rate.

The Merrill Lynch Factor Model achieved a 90% correlation with HRFI, and the Merrill Lynch Factor Model Exchange Series, which included the adjusted assets, had a correlation of 99.7% with the original model.

# 3. Discussion: ProShares Hedge Replication ETF

## What Are Alternative ETFs?
Alternative ETFs hold alternative investments like REITs (real estate), crypto-assets, high-yield bonds (less liquid), commodities, and alternative strategies. These strategies may include algorithm-based approaches if they can be delivered at a low cost.

Alternative ETFs can generally be defined as ETFs that:
- Belong to alternative asset classes.
- Are algorithm-based.
- Have leverage or short positions on indexes.

## ETFs vs. Hedge Funds
- ETFs are generally more liquid than hedge funds and do not require waiting periods for withdrawals.
- Hedge funds aim to generate $\alpha$ and outperform ETF benchmarks (whether they succeed is another story). As a result, hedge funds typically charge higher fees.
- Hedge funds take a bottom-up approach (dealing with illiquid securities, high-yield bonds, etc.), aiming to generate $\alpha$, while ETFs take a broader, top-down approach, focusing on macro-level factors.

## What Are the Indexes Mentioned?
- **HFRI**: An index that aggregates hedge fund returns.
- **MLFM**: The Merrill Lynch Factor Model, which statistically replicates the performance of the HFRI by analyzing key market factors.
- **MLFM-ES**: A variation of the MLFM that uses tradable securities to replace non-marketable components.
- **HDG**: Uses the MLFM-ES to replicate the HFRI.

## Concerns About MLFM Replicating HFRI
While the model achieves a high $R^2$, the replication involves multifactor regression, which could lead to high multicollinearity.

Indeed, the factors in the model exhibit considerable correlation:
- S&P US Equity with EFA US Equity: 86%
- EFA US Equity with EEM US Equity: 84%
- EFA US Equity with IWM US Equity: 78%
- S&P US Equity with IWM US Equity: 88%

## Is HDG's Delivery of Beta a Problem?
HDG acts as a passive "hedge fund," aiming to provide access to $\beta$ rather than generate $\alpha$. Direct hedge fund investment would be significantly more expensive and involve liquidity challenges, high fees, and other issues.

## Why Is HRFI So Different from the S&P 500?
HRFI includes hedge funds that do not necessarily invest in equities, providing substantial diversification. Additionally, hedge funds that invest in equities often hedge risks they are less familiar with, leading to less exposure to unwanted risks.

### How Well Does HDG Replicate HFRI?
HDG replicates HFRI reasonably well in terms of correlation (89%), but there are differences in level, skewness, and kurtosis.

While HFRI had better risk-adjusted returns compared to HDG, HDG exhibited less negative skewness (HFRI skewness: -0.98, HDG skewness: -0.24) and lower excess kurtosis (HFRI: 5.91, HDG: 1.78).

Overall, HDG is a fair replication, given that it uses six factors to replicate a vast array of possible hedge fund investments.
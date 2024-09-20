# 3. Case Study: The Risk of Stocks in the Long Run - Barnstable College Endowment

## Introduction
The college's policy was to spend between 4% and 5% of the endowment each year.

## Investment Philosophy
The investment committee believed that, in the long run, stocks would outperform safer asset classes such as bonds and Treasury bills. Since the short-term demands on the endowment were relatively small, the committee saw no point in sacrificing long-term returns by holding bonds and other assets that offered more short-term safety.

Currently, the portfolio composition is as follows:
- S&P 500: 40%
- Actively-managed portfolio: 30%
- Actively-managed portfolio of non-US stocks: 30%

These proportions were maintained through periodic rebalancing.

## Long-Run Risk
- Standard deviation increases with $\sqrt{T}$ (time).
- Returns increase with $T$.

In the long run, assets with higher expected returns tend to outperform those with lower expected returns with more certainty, as returns grow faster than the standard deviation.

## Ideas for Risk Mitigation
- **Put Options**: The committee considered selling put options on the S&P 500 (with dividends reinvested). These options were extremely expensive compared to the predicted probability of being executed.
- **Creation of a Trust**: A trust would own stocks in the S&P 500, with two classes of shares on the liability side: preference shares and common shares. Preference shareholders would receive the redemption value or the asset value after 30 years, while common shareholders would get any excess value. The redemption value was calculated as $1.06184^{30} = 6.05$ for each dollar initially invested. Barnstable College would retain the common shares and sell the preference shares to the market, thus raising cash and benefiting from the difference between the S&P's returns and the calculated $1.06184^{30}$.

In essence, both ideas aimed to hedge long-term risk, though they employed different mechanisms.

# 4. Discussion: The Risk of Stocks in the Long Run - Barnstable College Endowment

Barnstable College Endowment operated under the belief that, in the long run, stocks would outperform bonds. Is this a controversial stance? In the long-term, not really. Historically, stocks have indeed outperformed bonds in most long-term periods. However, over the mid- or short-term, this is not always the case.

The central question for Barnstable Endowment was: What is the probability that stocks will underperform bonds over 1, 2, 5, or 10 years?

Barnstable aimed to maximize long-run returns, showing little concern for short-term fluctuations or diversification.

## Calculating the Probability of Shortfall: Will Stocks Underperform Bonds?
Modeling returns over multiple periods can make probability calculations complex. However, log returns allow for more efficient calculations, as cumulative log returns are the summation of individual returns.

Assuming the normality of log returns, cumulative log returns are also normally distributed. The average period return $\bar{r}$ of cumulative returns can be represented as:

$\bar{r} \sim \mathcal{N}(\mu, \frac{\sigma^2}{h})$

Thus, the probability of stocks underperforming bonds is given by:

$\phi\left(-\sqrt{h} \frac{\mu - r_f}{\sigma}\right)$

Where $\phi$ denotes the CDF of a standard normal distribution. The larger $h$ (time), the smaller the probability that bonds will outperform stocks.

Results:
- 10 years: 16.4%
- 20 years: 8.4%
- 30 years: 4.5%

Though the probability diminishes quickly, the confidence interval expands over time.

## What Are They Overlooking?
- **Uncertainty of $\mu$**: The actual value of $\mu$ (expected return) is unknown and could deviate significantly from the estimate. If $\mu$ is lower than $r_f$, the probability of stocks underperforming bonds increases with time. For instance, if data from 2008 is included, the probability of underperformance would rise significantly.
- **Risk-Free Rate ($r_f$)**: The future risk-free rate is also uncertain. Beating a 6% return is impressive in most periods, but it might have been more prudent to consider excess returns over zero.
- **Institutional Constraints**: The endowment might not have the perseverance to maintain this strategy for 100 years. Drawdowns could cause the committee to reconsider, and it's possible that the portfolio manager would have been replaced before seeing long-term results. Institutional inertia might lead to a strategy shift after poor performance.

## How Were They Looking to Finance This?
- **Selling Puts on the S&P 500**: This strategy involves selling puts on the S&P to finance additional purchases of S&P shares. If stocks underperform, the puts would be in the money, requiring large payouts.
- **Trust Structure with Preference and Common Shares**: The trust structure would allow the endowment to capture the maximum returns of the S&P over 30 years, offset by 30 years of returns at the risk-free rate ($r_f$).

Ultimately, these two strategies aim to hedge against different risks and produce varying outcomes.

## Conclusion
Risk is heavily dependent on the investor's horizon. A 10-year investor in a 10-year treasury bond has essentially no market risk.

While the Barnstable case presents an intriguing long-term investment strategy, the statistics introduce enough uncertainty to warrant caution. Whether or not investments become safer in the long run is a complex question that requires careful analysis.
# 9. Hedge Funds
Actively managed funds generally perform worse than passive diversification. When accounting for fees, the results look even worse, as shown by Jensen's research.

Carhart found that funds which performed well in the past have around a 50% chance of doing well in the following year.

On the other hand, funds that performed poorly in the past are likely to continue doing poorly. The momentum strategy for hedge funds, especially shorting the underperformers, is effective according to Carhart.

## Uncertainty of a Fund's Mean Returns
Even in diversified funds, the volatility is significantly higher than the mean, leading to a lot of uncertainty, as the random component is considerably large.

Even if a sample shows a high mean return, in financial markets and with hedge funds, we cannot be statistically confident that next year's mean return will be similarly high.

Generally, we are not confident about the mean at all.

Judging actively managed hedge funds solely by their past performance and mean return doesn’t provide enough insight. The sample is not truly representative of the population when it comes to estimating the mean with confidence.

Allowing the data to speak for itself without deeper analysis often leads to poor conclusions. A more granular understanding of the decision-making process is needed.

Hedge funds typically do not provide daily data.

## Biased Mean Estimate (Survivor Bias)
If we only analyze statistics of current hedge funds or stocks, we likely see better performance than the actual population due to survivor bias. The data doesn’t account for funds that failed in the past due to poor performance, negative skewness, etc.

Research has shown that if we eliminate this bias between 1994-2003, hedge fund annual performance would have been reduced by half (~14% to ~7%).

A similar perspective applies when looking at stocks.

## Reporting Returns: Illiquid Assets
Hedge funds with illiquid assets often report a biased variance. Since their assets don’t trade frequently, they cannot report the actual value of the assets daily, leading to fewer price changes and an apparently lower correlation with the broader market. However, this lower volatility or correlation is misleading—the issue is the inability to measure risk properly. The reported values reflect a "smoothed" version of the prices.

For example, we could buy a share of SPY, lock it away for 100 years without measuring its value, and claim its market correlation is zero. Hedge funds with illiquid assets claiming low correlation to the SPY operate under a similar logic.

## How to Address This?
Asness, from AQR, proposed a clever solution: regressing illiquid funds not only with the SPY’s returns but also with the SPY’s lagged returns. The illiquid hedge funds displayed significant lagged betas in this regression, which would not occur if the hedge funds were liquid (as liquid returns have low autocorrelation).

The betas for illiquid funds are much higher than they appear!

## Detecting Option-Like Strategy: Quadratic Equation
If the beta for the quadratic of market returns is positive, the hedge fund is likely buying put options. If the quadratic of market returns is negative, the hedge fund is likely selling put options.

\[
\tilde{r}_t^i = \alpha + \beta_{0} \tilde{r}_t^m + \beta_{1} (\tilde{r}_t^m)^2 + \epsilon_t
\]

- If \(\beta_1 > 0\): likely buying put options.
- If \(\beta_1 < 0\): likely selling put options.

This can also be seen in a piecewise regression, using the positive and negative side of market returns:

\[
\tilde{r}_t = \alpha + \beta_0 r_t^m + \beta_1 \max(\tilde{r}^m - k_1, 0) + \beta_2 \max(k_2 - \tilde{r}^m_t, 0) + \epsilon
\]

- If \(\beta_1 \neq 0\): likely buying/shorting call options.
- If \(\beta_2 \neq 0\): likely buying/shorting put options.

## Fees and Flows
For hedge funds, the expected inflow is heavily influenced by past performance. Investors tend to follow whichever fund was "hot" last year, though there is debate about whether this behavior is rational.

As hedge funds mature, investors focus more on long-term returns than on short-term performance.

For young hedge funds, the first three years are critical: poor performance can mean the fund won’t survive, while strong performance typically leads to a significant inflow of capital.

## Lock-Up Periods
Lock-up periods constrain both me and all other hedge fund investors, potentially preventing situations similar to the collapse of LTCM.

## Hedge Fund Fees
Initially, hedge fund fees were typically 2% of assets under management plus 20% of performance.

Generally, the performance fee is subject to a high-water mark, requiring the fund to make up for previous losses before collecting fees on profits.

Today, fees are lower due to increased competition in the industry.

## Hedge Fund Manager Incentives
Because the hedge fund manager’s payoff resembles a call option on the portfolio value (though not exactly), managers often take more risks than investors might prefer. This dynamic also incentivizes managers to perform.

If the portfolio is below the high-water mark, managers are incentivized to take bigger risks (higher volatility).

Covenants are commonly used to ensure portfolio managers behave responsibly in such situations.
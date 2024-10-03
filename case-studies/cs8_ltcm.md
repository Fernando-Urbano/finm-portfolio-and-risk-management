# 8. Case Study: Long-Term Capital Management, L.P.

Due to limitations imposed by available market liquidity, the principals recognized that it would be impractical to increase position sizes in proportion to the performance-induced increase in capital.

LTCM adopted a long-term financing structure to withstand short-term market fluctuations.

In many of its trades, the firm acted as a seller of liquidity, taking both long and short positions.

The firm's positions were diversified across many markets and leveraged to increase exposure.

LTCM was headed by John Meriwether, who had gained fame as a pioneer of fixed income arbitrage and had a remarkable historical performance in the field.

The investors were a variety of financial institutions and wealthy individuals (but predominantly financial institutions).

Most of the firm's investments were in non-U.S. entities.

The fund employed a structure involving multiple entities to accommodate the various tax, regulatory, and other needs of its investors.

The fund was compensated with 0.5% per quarter plus 25% of a "high water mark."

The fund's returns were exceptional.

LTCM primarily engaged in convergence and relative value strategies: taking long and offsetting short positions in instruments that were close substitutes.

With attractive financing rates, these positions could generate significant profits with low risk.

LTCM had a strong preference for strategies that exposed the fund to minimal or no default risk, generally avoiding long-only positions in high-yield corporate bonds or emerging market sovereign debt. Nevertheless, some strategies involved going long on sovereign debt and short on corporate bonds.

The firm often built models to identify mispricing created by large institutional demand.

# 8. Discussion: Case Study Long-Term Capital Management, L.P.

## Mean, Skewness, Volatility, and Sharpe Ratio

When evaluating a hedge fund with a very high Sharpe ratio, we should be cautious and not rush into investing.

It’s important to consider the skewness and kurtosis of the returns.

Very negative skewness indicates that, on average, there are consistent returns, but occasionally, there are significant losses. This asymmetry between gains and losses is critical to understand.

If a hedge fund has highly negative skewness, it is often described as "taking the stairs up and the elevator down." With very negative skewness, the Value at Risk (VaR) could be disproportionately worse compared to an asset with a similar return.

Kurtosis, which measures the fatness of the distribution tails, shows the likelihood of extreme returns. High kurtosis means there is a higher probability of returns deviating far from the mean. We should avoid hedge funds with both high kurtosis and very negative skewness.

## Strategy: Selling Out-of-the-Money Put Options

If a hedge fund sells out-of-the-money put options each month, it can generate strong returns on average. However, during a few disastrous months, it could incur significant losses.

This strategy may produce an impressive Sharpe ratio until the hedge fund faces potential bankruptcy. In previous backtesting, a hedge fund employing this strategy would have gone bankrupt in 1998, 2008, and nearly in 2020 if it had been aggressive enough (2% per month).

After a crash, the Sharpe ratio would plummet, and the skewness would turn extremely negative.

# LTCM

## What Was the Investment Strategy of LTCM?

LTCM primarily focused on relative value strategies: the firm aimed to understand and bet on securities with spreads that would eventually converge. They tried to predict the probability and timing of this convergence, especially in fixed income.

## Did Their Trades Have Negative Skewness?

Yes, LTCM's trades had negative skewness: if the trades converged, they yielded small returns, but if they did not converge, which was rare, the losses could be significant.

They hoped that their trades were not highly correlated, meaning that not all spreads would widen simultaneously. If one spread widened, they expected the others to remain stable.

## How Did They Manage Risk?

In times of crisis, correlations between assets increase significantly. LTCM's risk management considered these heightened correlations, focusing on crisis scenarios where they were much larger.

Their risk management team took a conservative approach, preparing for the worst-case scenarios, especially spikes in correlation.

## Where Did They Get Their Funding?

To execute their trades, LTCM needed access to low-interest-rate funding. This was crucial because the spreads they traded were small, and the trades would only be profitable with a very low "fund cost."

Therefore, they used a lot of leverage, often borrowing through REPOs. While the standard REPO term in markets is overnight, LTCM frequently used longer terms, sometimes up to a month.

Borrowing money through longer-term REPOs reduced the pressure on LTCM: with short-term REPOs, interest rates would change quickly if market conditions worsened, but longer-term REPOs allowed for more stability. This approach was conservative.

## Debt Fund

Some of LTCM's convergence trades were leveraged up to 20x.

They also relied on loans from banks, which usually included agreements that allowed the banks to cancel the loan if there was a "material change" in risk. Essentially, banks would "loan the umbrella but take it back when it rains."

LTCM had so much market power that it could avoid taking loans with these conditions.

## Equity Fund

The equity fund was primarily institutional. Additionally, LTCM instituted "lock-ups" to ensure that not too many investors had their lock-ups expiring in the same month.

## Avoiding Systematic Factor Exposure

LTCM aimed to hedge against systematic factors. They preferred positions that were not exposed, or were hedged, against large factors such as the S&P or the overall bond market.

Engaging in convergence trades allowed LTCM to be more confident in their expected returns. Moreover, if trades diverged further, they viewed it as an even better opportunity in the long run. The problem, however, was surviving until the long run.

## Liquidity or Investor Problem

Investors could become scared and withdraw their money, or liquidity conditions could worsen. Even though the long-term prospects were promising, LTCM might not make it to the long run.

This ultimately happened, and LTCM was forced to close.

In the end, LTCM had to sell its trades to other firms, but the trades would have eventually made money.

## What Is the Case About?

The case does not directly mention that LTCM went bankrupt. Instead, it discusses LTCM’s equity capital problem.

The firm was making so much money that equity capital became a burden: there were not enough opportunities for the amount of money people wanted to invest.

LTCM returned capital to some equity investors, prioritizing those who had invested first and seeking to maintain very high returns.

In hindsight, LTCM should have reduced its leverage instead of returning capital.

## Why Was LTCM Amazing?

In terms of net returns, LTCM's performance was not superior to the S&P. However, the most impressive aspect of LTCM was its lack of correlation with the S&P. This uncorrelated alpha made it incredibly attractive, and investors were eager to participate.

## How to Measure Tail Risk?

Tail risk can be assessed by regressing the hedge fund's returns against the square of the market's returns.

This analysis can show what happens during extreme market movements.

Asymmetry can also be detected by looking at options in the S&P.
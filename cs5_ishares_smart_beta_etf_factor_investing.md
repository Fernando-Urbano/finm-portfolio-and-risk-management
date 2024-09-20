# 5. Case Study: Smart Beta Exchange-Traded Funds and Factor Investing

## Introduction
The iShares Factors Strategy Group was considering launching ETFs known as smart beta funds.

These smart beta ETFs' weighting schemes were based on firms' financial characteristics or properties of their stock returns.

The new smart beta multifactor ETF would expose investors to the market value of the firm (MKT), relative value based on financial position (HML), quality, and momentum.

While these factors existed individually for different firms, no firm had yet combined all the factors into a single fund.

# 5. Discussion: Case Study on Smart Beta Exchange-Traded Funds and Factor Investing

## What is the difference between smart beta and traditional ETFs?
Smart beta ETFs aim to track specific factors instead of tracking a sector or the entire market.

They became popular in the early 2010s due to their ability to track well-known financial factors.

While manually creating portfolios based on factors can be complex (requiring the buying/selling of multiple stocks and frequent rebalancing), investing in ETFs makes it much simpler.

These ETFs have made it easier for retail investors to allocate capital to factor-based strategies.

## Is it possible for everyone to have long exposure to a particular factor? For example, can we all have long exposure to the market or the value factor?

Not everyone can invest in the value factor simultaneously.

However, we can all invest in the market factor: the market, by definition, represents the portfolio of all investors combined.

Factors such as momentum, value, and size involve tilting away from the market by going long in certain stocks and shorting others. We cannot all be short certain stocks since the net buys and sells must equal the total shares outstanding.

In contrast, being long the market doesn't require anyone to be short the market for it to make sense. We can all be long the market!

Thus, not everyone can be a momentum or value investor. Whatever premium is gained from these factors must be sustained by someone taking the opposite position.

## Common Factors
- MKT: Market
- SMB: Small minus Big Market Cap
- HML: High minus Low Book/Market Ratio
- RMW: Robust minus Weak Profitability
- CMA: Conservative Minus Aggressive in Investment
- UMD: Up minus Down, Momentum

The factors with the best Sharpe ratios are MKT and RMW (0.5305 and 0.5376, respectively). The value factor (HML) has a lower Sharpe ratio (0.2529). However, we cannot evaluate HML solely by its Sharpe ratio; correlations with other factors are essential to understanding its importance.

HML has low correlation with most other major factors except CMA. This is why companies like AQR highlight the value factor's importance, particularly for diversification. AQR even suggests in one paper that the CMA factor may be unnecessary if value is measured correctly, as CMA is nearly a value factor.

Empirical evidence shows that HML is useful when combined with RMW for diversification.

SMB, on the other hand, has such a low mean excess return that we cannot be certain it provides a positive return.

Overall, correlations with the market factor are low because the factors are constructed as long-short portfolios. They are also designed to minimize correlations with each other to maximize statistical power.

### Tangency of the Portfolio
The tangency portfolio reveals which factors are most significant in explaining systematic risk.

When considering all six factors, the highest weights in the tangency portfolio are:

1. CMA
2. RMW
3. MKT
4. UMD
5. SMB
6. HML

The low weight for HML is due to its high correlation with CMA.

If we restrict the portfolio to MKT, HML, SMB, and UMD, all factors except SMB receive reasonable weights. SMB has a near-zero weight. This aligns with current quantitative strategies, where the SMB factor is often excluded.

SMB was more important in the past, but as investors began to recognize its premium, it diminished.

There were similar expectations for momentum, where many believed that momentum's premium would disappear as it became more widely recognized. The notion that momentum was simply a behavioral bias led Fama and French to exclude it from their 5-Factor Model.

However, subsequent research demonstrated that momentum continues to exhibit statistical significance.

Momentum also shows significant effects in commodities, global equities, bonds, and other asset classes.

## Model Fit: Time-Series vs. Cross-Sectional MAE
The Cross-Sectional MAE will always be smaller than the Time-Series MAE. This occurs because, in the cross-section, factor premiums are optimized to best fit the cross-sectional data, while in the time-series, factor premiums are based on the average sample excess returns.

By construction, the cross-sectional approach involves more parameters, allowing it to better fit the data.

## Why is the Time-Series MAE larger for factor models with more factors?
When comparing the MAE of time-series and cross-sectional regressions, we find that factor models with more factors tend to perform better in the cross-section but worse in the time-series. For example, the time-series MAE is smaller for CAPM (2.12%) compared to the Fama-French Five-Factor model (2.98%).

This occurs because the MAE in this context relates to the size of the $\alpha$ rather than $R^2$. If we were focusing on $R^2$, adding more regressors would necessarily reduce the MAE. However, increasing the number of regressors does not guarantee that the $\alpha$ will shrink.

In the cross-section, on the other hand, the focus is on maximizing the $R^2$. By adding more parameters, the fit will generally improve, unless we impose constraints (e.g., using the time-series mean as $\lambda$) or omit an intercept in the cross-sectional regression.
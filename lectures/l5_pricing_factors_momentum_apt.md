# 5. Pricing Factors (Summary of notes)

## Time-Series Test of a Factor Model
A pricing model works if the $\alpha$ is statistically insignificant.

We focus on the $\beta$'s of the model when we already believe the model is valid and aim to calculate the $\mathbb{E}[\tilde{r}^i]$ for asset $i$. In other words, the $\beta$'s are relevant when we are users of the model: they indicate which assets have high or low mean expected returns.

We do not focus on $R^2$: the $R^2$ would only matter if the factors of a pricing model were used to hedge or replicate instead of for pricing.

## Cross-Sectional Test
We can also test the model in a cross-section:

The cross-sectional regression can be expressed as:

$\mathbb{E}[\tilde{r}^i]=\eta+\beta^{i, 1}\lambda_{1}+\beta^{i, 2}\lambda_{2}+\beta^{i, 3}\lambda_{3}...+\beta^{i, n}\lambda_{n}+\nu^i$

The $\beta^{i, 1}$ to $\beta^{i, n}$ form the matrix of features, while the $\lambda_{1}$ to $\lambda_{n}$ represent the parameters.

The new intercept is denoted by $\eta$.

This cross-sectional test allows us to evaluate the factor model using multiple test assets.

In the cross-section, we care about the $R^2$ of the regression. For a perfect pricing model, we expect an $R^2$ close to 100% (though not exactly 100%, as there can still be sample bias).

To perform the cross-sectional test, we must first carry out the time-series regressions on the betas.

## Historical Results for the CAPM in Fama-French Test Assets
Using the Fama-French test assets, we can perform the time-series and cross-sectional tests, leading to some conclusions:
1. In the time-series, the alphas are considerably large and sometimes statistically significant.
2. In the cross-section, the $R^2$ is low (25.8% in the sample), indicating that CAPM does not fit the data well.
3. If we allow for a proper cross-sectional regression, $\lambda_{m}$ (the market premium) is -0.0982, which contradicts the historical market premium of 0.0802.

## Fama-French Factor Model
The expected excess return of any asset is a linear combination of three $\beta$'s:
- Market Factor
- Value Factor
- Size Factor

This is a strong statement: it implies that nothing else matters in determining which assets have high mean returns.

In the rational interpretation, this only holds if investors are risk-averse to these $\beta$'s: if they are, the prices of assets with these $\beta$'s become smaller, leading to higher expected returns. In a behavioral interpretation, investors may be systematically biased against certain characteristics, though not necessarily due to extra risk.

### How Important Are These Betas?
We scale each of the betas by their respective premiums.

### Size
The Size Factor relates to the market value of stocks. In the size factor, we go long on small stocks and short on big stocks. There are multiple ways to construct this factor.

### Why Do We Short and Long in the Factor?
Without shorting big stocks, we would have considerable exposure to the overall market. Shorting the big stocks helps hedge the correlation between small and large stocks, making the factor behave differently from the market.

### Value
The Value Factor is tied to the Book-to-Market Ratio of stocks: we go long on value stocks and short on growth stocks. Specifically, we long stocks with high B/M ratios and short stocks with low B/M ratios.

Book-to-market implies strong accounting fundamentals relative to the stock's price.

### Does This Mean Small or Value Stocks Have High Mean Returns?
Not necessarily! These factors suggest that stocks with a positive relationship to the factors will have high mean returns. It’s about how the company’s returns behave, not its size or label.

For instance, a stock with a high B/M ratio but behaving like a growth stock will have low expected returns. Conversely, a stock with a low B/M ratio behaving like a value stock will have high expected returns.

The key determinant of expected return is the $\beta$, not the stock's characteristics!

## Other Popular Factors
Other well-known factors include:
- Price movement
- Volatility
- Profitability (added later in the Fama-French 5 Factor model): go long on profitable firms and short on less profitable ones.
- Investment (also added in the 5 Factor model): go long on stocks that invest less and short those that reinvest heavily, based on the notion that overinvestment often hurts returns.

## What is the Performance of the Fama-French Model?
Though Fama-French improves on CAPM, it still doesn’t capture all systematic risk.

This factor model is the most recognized and serves as a foundation for discussing more complex models.

The HML (Value factor) remains widely used, but the SMB (Size factor) has lost popularity.

Today, there is a proliferation of factors and factor models, often referred to as the "zoo factor."

## The Tangency Portfolio as a Factor Model for In-Sample Data
We can create a "perfect" factor model for a given set of test assets. This perfect model would have an $R^2$ of 100%, $\eta$ of zero, and would perfectly price all test assets.

This is the tangency frontier portfolio of the test assets. While perfect in-sample, this model wouldn’t generalize well out-of-sample due to the instability of the variance-covariance matrix.

The tangency portfolio perfectly prices the in-sample test assets, but its instability makes it unsuitable for out-of-sample data.

Other factor models help avoid overfitting inherent in the tangency portfolio.

## Tangency Portfolio to Understand Factor Importance
The tangency portfolio helps us identify the most important factors. Factors with little weight are likely unimportant.

Recent research shows relevant weights for the market and value factors, while statistical analysis reveals the size factor's irrelevance.

## Can We Use LASSO to Identify Important Factors?
No. LASSO aims to maximize the time-series $R^2$ out-of-sample, but our goal is to minimize $\alpha$ rather than maximize $R^2$.

# Momentum
Momentum is not part of the Fama-French 3 Factor model but is one of the most famous strategies.

There were discussions about adding momentum to the Fama-French 5 Factor model, but Fama and French ultimately did not include it, despite its popularity.

## What is Momentum? Return Autoregression
For the overall market index, there is no strong evidence of serial correlation, positive or negative. This can be tested by regressing the index's return on its past return:

$r^{m}_{t+1}=\alpha+\beta{r^{m}_t}+{\epsilon_{t+1}}$

The $\beta$ is typically near zero and statistically insignificant, as any detectable serial correlation would be quickly exploited by traders.

While there may be slight autocorrelation, the small $R^2$ would indicate that exploiting it carries significant risk.

## Momentum as a Strategy
If we observe a small positive $\beta$ in the above regression, we can develop a strategy by going long on stocks with high past returns and short on those with low past returns.

Betting on multiple stocks rather than just one reduces variance, even with a small positive bias. The strategy targets stocks with extreme returns to maximize the bias and reduce volatility.

## Implementing a Momentum Strategy
A momentum strategy ranks securities based on recent returns:
- Go long on recent winners and short recent losers.
- Regularly re-rank the "winners" and "losers."

Typically, momentum strategies use 12 or 13-month returns, which helps reduce transaction costs.

Momentum strategies have been successful across asset classes, including equities, government bonds, currencies, and commodities.

## Is Momentum Just High Market Beta?
Momentum strategies are not solely explained by market beta. When regressed by the CAPM, momentum strategies produce a positive $\alpha$, indicating that market risk doesn’t account for all excess returns.

Momentum's Sharpe ratios are impressive: U.S. stocks (0.86), Global Stocks (1.21), Currencies (0.69), Commodities (0.77) over the period 1972-2011.

## Why Does Momentum Work?
It remains unclear why momentum generates excess returns. Various theories have been proposed, such as portfolio rebalancing risk, but no single explanation has been conclusively proven.

# APT (Arbitrage Pricing Theory)
APT (Arbitrage Pricing Theory) links linear factor decomposition to linear factor pricing models.

If factors work well for linear factor models (for hedging and decomposition), they should also work for pricing.

Given factors $x$, we can describe any asset returns $r$ using the following equation:

$\tilde{r}^{i}_t=\alpha^{i}+(\beta^{(i, x)})'x_t + \epsilon_t$

The factors explain everything except the idiosyncratic components of the assets.

## Diversified Portfolio in the APT Framework
By constructing a diversified, equally weighted portfolio using "n" assets, we can express its return as:

$\tilde{r}^p_t = \frac{1}{n} \sum_{i=1}^{n} r^i_t$

$\tilde{r}^p_t = \alpha^p + (\beta^{p, x})' x_t + \epsilon^p_t$

As $n \rightarrow \infty$, the idiosyncratic components wash away, and the return of the portfolio becomes:

$\tilde{r}^p_t = \alpha^{p} + (\beta^{p, x})' x_t$

Since $\alpha^{p}$ must be zero to prevent arbitrage, we have created a perfect pricing model.

## Relationship Between Factor Pricing and Decomposition
A perfect linear factor decomposition implies a perfect linear factor pricing model. However, the reverse isn’t true: factors that are perfect for pricing may not be perfect for decomposition.

In practice, we don’t achieve perfect decomposition, but the theory motivates the search for factors that approximate the ideal.

# Deriving the CAPM: Why Might It Work?
The CAPM might work if returns are jointly normal and i.i.d. across periods. Under these conditions, all investors would be mean-variance investors, holding a combination of the tangency portfolio and the risk-free rate. Aggregating across all investors would produce the tangency portfolio.
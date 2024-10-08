# 7. Forecasts

## Risk Premia Across Assets
Does the risk premium of individual assets change over time?

It may be that we live in a world where the expected return is always the same, and the actual return is just "luck of the draw." Alternatively, we can consider the premium as changing over time. If the conditioning is stable, the expected value for excess return is independent of time:

$$\mathbb{E}_t[\tilde{r}^i_{t+1}] = \mathbb{E}[\tilde{r}^i]$$

However, if we believe that the risk premium changes, then:

$$\mathbb{E}_t[\tilde{r}^i_{t+1}] = f(X_t)$$

If this is true, we can attempt to understand the function $f(X_t)$ and draw insights from it. In a dynamic world, we would know when to increase or decrease asset weights accordingly.

The classical view, on the other hand, suggests that mean returns remain constant.

## Linear Methods
If we believe that risk premia vary over time, we must specify a functional form for $f(X)$. Linear models are one option.

Linear regression allows us to compute statistics and metrics more easily. Additionally, linear regression provides the best linear estimator for such a function.

Even today, linear regression is widely used. In forecasting regressions, we often employ regression with lagged features. This allows us to avoid predicting the features as well:

$$\tilde{r}^i_{t+1} = \alpha + \beta x_t + \epsilon_{t+1}$$

If the forecast is very good, we would expect a reasonably high $R^2$. Forecasting is challenging, and high $R^2$ values are rare, but we need a sufficiently strong $R^2$ to believe that our $f(X_t)$ makes sense.

It’s not enough to have a significant $\beta$. If $\beta$ is significant but $R^2$ is low, it means that while the effect exists with statistical confidence, it is practically insignificant. In time-series forecasting, we definitely care about $R^2$!

## Classic View vs Modern View
The classic view asserts that the unconditional expectation is the conditional expectation, and returns cannot be forecasted using $f(X_t)$.

This view also suggests that price growth follows a random walk (with drift):

$$\log(P_{t+1}) - \log(P_t) = \text{constant} + \epsilon_{t+1}$$

## Is the Risk-Free Return Autocorrelated?
Some assets, like the risk-free rate, are relatively easy to predict. For instance, risk-free rate returns can be predicted with high confidence.

## Fundamental Features: Macroeconomic Data, Stock Fundamentals, etc.
While the risk-free rate is highly autocorrelated, other assets do not exhibit this property. Macroeconomic data or stock fundamentals can be valuable in improving these models.

We can also adjust the forecasting horizon. For example, GMO attempts to predict over months and years whether the overall environment favors bonds, equities, gold, or commodities.

Better predictions can lead to changes in optimal weights in a mean-variance optimization.

# Dividend-Yield Forecasting
The dividend-yield is an interesting feature for forecasting.

Dividend-yield refers to the dividend-price ratio, $\frac{D_t}{P_t}$. Historically, it has been a good predictor, with mathematical justification beyond mere speculation.

By definition:

$$R_{t+1} = \frac{P_{t+1} + D_{t+1}}{P_t}$$

Rearranging:

$$R_{t+1} = \left(\frac{D_t}{P_t}\right) \left(\frac{D_{t+1}}{D_t}\right) + \left(\frac{P_{t+1}}{P_t}\right)$$

The expected return is:

$$\mathbb{E}_t[R_{t, t+k}] = DP_t \cdot \mathbb{E}_t\left(\frac{D_{t, t+k}}{D_t}\right) + \mathbb{E}_t\left(\frac{P_{t, t+k}}{P_t}\right)$$

A higher $DP_t$ implies a higher expected return.

The classical view suggests that a higher $DP_t$ would correspond with smaller dividend or price growth, keeping the expected return constant, thus eliminating any predictive power from dividend yields.

However, empirical evidence shows the opposite, especially over longer horizons. According to one study, $DP$ can explain returns with an $R^2$ of 31% over five-year horizons, but only 1% for monthly returns and 9% for one-year returns.

This empirical finding holds because $DP$ has a high autoregressive coefficient at monthly frequencies (around 98%):

$$DP_{t+1} = \alpha + \beta DP_t + \epsilon_t$$

On a monthly basis, a high $DP_t$ has limited potential to increase returns. But, over time, compounding this effect leads to higher returns for assets with higher $DP_t$.

Other forecasting signals may have a greater long-term impact, including:
- **Risk-free rate**: Although highly autoregressive, the risk-free rate has minimal impact in the short term, but its effects compound over time.
- **Earnings/Price (EP) ratio**: Similar to $DP$, the $EP$ ratio reflects firm earnings rather than dividends. While the classical view would argue that higher $EP$ would be offset by future earnings or price changes, empirical data refutes this, as with $DP$.

In general, some signals are better for forecasting short-term horizons, while others perform better over the long term. Signals that are highly autoregressive increase in importance over time but are more difficult to assess with statistical power.

# Other Forecasting Variables
- Cyclically-adjusted price-earnings ratios
- Macroeconomic indicators
- Inflation and interest rates
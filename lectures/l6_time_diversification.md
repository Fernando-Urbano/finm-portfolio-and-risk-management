# 6. Time Diversification (Summary of notes)

In previous lectures, we discussed how to invest across assets at a given time. Now, in time diversification, we explore how to invest across time.

We often prefer to use logarithms in this context. Considering i.i.d. log returns:
- The cumulative return is the sum of returns.
- The expected return for a given period $h$ is the $\mu$ of a given period multiplied by $h$:

$$\mathbb{E}[\texttt{r}_{t, t+1}] = \mu$$

$$\mathbb{E}[\texttt{r}_{t, t+h}] = h\mu$$

where $\texttt{r}$ is the log return.

- The covariance becomes:

$$\text{var}\left[\texttt{r}_{t,t+h} \right] = \sum_{j=1}^{h} \sum_{i=1}^{h} \text{cov} \left[\texttt{r}_{t+i}, \texttt{r}_{t+j} \right]$$

We expect those covariances to be quite small.

## AR(1) and Scaling Variance
An AR(1) is an autoregressive model that is popular in time-series statistics:

$$\text{cov}\left[\texttt{r}_{t}, \texttt{r}_{t+i} \right] = \rho^i \sigma^2$$

$$\text{corr}\left[\texttt{r}_{t}, \texttt{r}_{t+i} \right] = \rho^i$$

Based on an AR(1) model, the scaling of the variance changes:

- If $\rho^i = 1$, the standard deviation grows linearly with time: $h\sigma$.
- If $\rho^i = 0$, the variance grows linearly with time: $h\sigma^2$.
- If $\rho^i = -1$, the return becomes riskless and the variance is 0.

An example of an asset with $\rho^i < 0$ is bonds, especially treasury bonds. This occurs because the bond will eventually reach a fixed price (as it pays a fixed amount at maturity). If returns are low now, future returns must be higher to compensate, leading to mean reversion or negative serial correlation in bonds.

## Auto-correlation of Returns and the Consequence on Sharpe Ratio
If $\rho^i = 1$, the Sharpe ratio remains constant as the horizon increases because both volatility and returns scale linearly with time.

However, if $|\rho^i| < 1$, the Sharpe ratio increases over longer horizons, indicating risk reduction over time for a unit of excess return.

For $\rho^i = 1$:

$$SR(\texttt{r}_{t, t+h}) = SR(\texttt{r}_{t})$$

For $|\rho^i| < 1$:

$$SR(\texttt{r}_{t, t+h}) > SR(\texttt{r}_{t})$$

For $\rho^i = 0$:

$$SR(\texttt{r}_{t, t+h}) = \sqrt{h} SR(\texttt{r}_{t})$$

Since $\rho^i = 1$ is rare, the Sharpe ratio typically increases over longer horizons, benefiting long-term investors. For instance, endowment investors need not be as concerned about short- or medium-term risks. They benefit from time diversification, as the Sharpe ratio improves by holding returns from different periods, much like diversifying across different assets.

## Mean Annualized Returns
The annualized mean (log) returns on an "h"-period investment, $\texttt{r}_{t, t+h}$, is:

$$\frac{\texttt{r}_{t, t+h}}{h} = \frac{\sum_{i=1}^{h}\texttt{r}_{t+i}}{h}$$

For any $\rho$:

$$\mathbb{E}[\tilde{r}] = \mu$$

Regardless of the autocorrelation of returns, the average return is $\mu$. The larger the sample size, the more accurate this estimate becomes.

For $\rho = 0$:

$$Var[\tilde{r}] = \frac{\sigma^2}{h}$$

This decreasing variance gives higher certainty that the sample mean return will converge to the population mean. This is why stocks are considered safer in the long run: their average returns converge to the population mean over time.

## Why Stocks Are Not Necessarily Safer in the Long Run
Although asset allocators argue that stocks are safer in the long run, this is not always true. While the average return becomes more certain over time, the volatility of cumulative returns increases as $h$ grows.

The cumulative returns compound over time, expanding the variance. For example, a young student and an older grandparent may have different cumulative returns over their lifetimes. The student's total returns could fluctuate much more than the grandparent's due to this growing variance.

Therefore, time diversification is nuanced. The Sharpe ratio improves over time, but while the average return becomes safer, the cumulative performance becomes riskier.

Empirically, time diversification is real: for market returns, the autocorrelation is very low, leading to higher Sharpe ratios over longer time horizons. However, for the risk-free rate, autocorrelation is higher.

## Long-Run Uncertainty
In conclusion, while Sharpe ratios increase in the long run, this doesn't mean that investments become safer, as cumulative returns become more volatile. In the long run, investors receive more excess returns per unit of risk taken.

## Predicting with Factor Models
Once we have a model, we can use it to derive the $\mathbb{E}[r_a]$ for any asset and allocate accordingly.

Although factor models may not forecast well for individual assets, they offer several advantages:
- They provide a foundation for building more complex models.
- They offer insights into risk premia.
- They are useful for efficient trading (e.g., AQR and DFA).
- They provide non-biased pricing for assets, even if individual forecasts are imperfect.

Factor models aim to forecast returns in a consistent way across all assets, avoiding internal contradictions.

## Sharpe Ratio and Factor Models
In the CAPM, the Sharpe ratio of any asset is the Sharpe of the market multiplied by the correlation between the asset and the market:

$$\frac{\mathbb{E}[\tilde{r}^i]}{\sigma^i} = (\rho^{i, m}) \frac{\mathbb{E}[\tilde{r}^m]}{\sigma^m}$$

In other factor models, the Sharpe ratio of any asset is the correlation between the asset and the tangency portfolio of the factors.

## Economic Factors (CCAPM)
Factor pricing models can use economic data instead of returns, such as:
- GDP growth
- Recession indicators
- Monetary policy indicators
- Market volatility

For non-return factors, the premium is represented by $\lambda_{nf}$, which indicates the relationship between the asset and the non-return factor.

## Factor-mimicking Returns
If we identify a non-return factor, we can create factor-mimicking returns by projecting the non-return factor onto traded returns.

## Fama-MacBeth Procedure
The Fama-MacBeth procedure addresses time-varying volatility and $\beta$'s, providing a more flexible model for $\beta^{i, z}_t$. This is especially important for individual assets.

The two steps are:
1. Estimate $\beta_t$:

$$\tilde{r}_t^i = \alpha^i + \beta_t^{i, z} z_t + \epsilon^i_t$$

2. Estimate $\lambda$, $\nu$:

$$\tilde{r}_t^i = \beta_t^{i, z} \lambda_t + \nu^i_t$$

From this, we can calculate the average premium ($\lambda$) and average $\nu^i$, allowing for more accurate asset pricing.

This allows a more flexible model for $\beta^{i, z}_t$.

One possible way to make these estimates even better would be to use the GMM (Generalized Method of Moments), which would account for ay serial correlation, and for imprecision of the first-stage (time-series estimates).

This method becomes even more important if we are using single assets as test assets. If we are working with portfolios, we will have test assets that have more stable $\beta$'s.
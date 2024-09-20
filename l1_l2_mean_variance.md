# 1. Optimizing Risk and Return
The risk of a portfolio is a non-linear combination of the risks of the assets. In frictionless markets, we can derive a solution for the optimal portfolio allocation, leveraging this non-linearity of risk.

Optimal portfolios aim to maximize returns and minimize risk.

### Why Should I Look at Excess Returns?
Excess returns are already adjusted for the level of risk-free interest rates available in the market. They show how much an investment is earning over the risk-free rate. Dealing with excess returns is especially crucial for comparing investment returns that occur at different points in time because the opportunity cost (the risk-free rate) varies over time.

For instance, a Hedge Fund performing at 5% during the low-interest COVID era (2021) is more impressive than achieving the same return today. Referring to excess returns instead of standard returns standardizes performance across different time periods.

Moreover, working with excess returns allows us to derive the tangency portfolio using an analytical formula, which is one of the most useful portfolios in mean-variance optimization.

### Mean and Risk of Portfolio (When Do We Have Diversification?)
As shown below, the mean of a portfolio is a linear combination of the means of the assets, weighted according to the proportion assigned to each asset.

The variance of the portfolio, however, is only a linear combination of the variances of the assets if the correlation between the assets is equal to 1.

${\mu}_{p}=w{\mu}^{b}+(1-w){\mu}^{s}$

${\sigma}_{p}^{2}=w^{2}{\sigma}_{b}^{2}+(1-w)^{2}{\sigma}_{s}^{2}+2w(1-w){\rho}{\sigma}_{s}{\sigma}_{b}$

${\sigma}_{p}^{2}=w{\sigma}_{b}^{2}+(1-w){\sigma}_{s}^{2}$;     if ${\rho}=1$

If the correlation is perfect, the volatility behaves like the mean: it becomes proportional to the asset allocation weights. In this case, and only in this case, volatility is linear.

On the other hand, if ${\rho}<1$:

${\sigma}_{p}<w{\sigma}_{b}+(1-w){\sigma}_{s}$

We call a portfolio diversified when ${\rho}<1$, as the volatility of returns is less than linear.

Some people claim that ${\rho}$ (correlation) must be 0 or negative for diversification. This is incorrect. The only requirement for diversification is ${\rho}<1$.

For example, a portfolio with two stocks can still be diversified even if their correlation is 70%.

### How to Create a Perfect Hedge?
If ${\rho}=-1$ and you have two assets in the portfolio, you can create a portfolio with zero volatility (zero risk) by correctly specifying the weight proportions.

To achieve ${\sigma_{p}}=0$:

$w_{s}/w_{b}=\frac{{\sigma}_{b}}{{\sigma}_{s}}$

### Allocation Among "n" Assets and the Necessary Covariance to Nullify Risk
Consider an equally-weighted portfolio with $w^{i}=1/n$ for each asset $i$.

The portfolio variance is:

${\sigma}_{p}^{2}=(1/n^{2}){\sum_{i=1}^{n}}{\sigma}_{i}^{2}+(1/n^{2}){\sum_{i{\neq}j}}{\sum_{i=1}^{n}}{\sigma}_{i, j}$

Taking the average of the variances and covariances, rather than summing each individually, gives us:

${\sigma}_{p}^{2}=(1/n)avg[{{\sigma}_{i}^{2}}]+((n-1)/n)avg[{\sigma}_{i, j}]$

As $n$ approaches infinity, the portfolio variance becomes the average covariance of the assets.

The result shows that in portfolios with a large number of assets, as the weights get smaller, the covariance between the assets becomes proportionally more important than the variance of the individual assets.

This means that for large hedge funds, the individual volatility of a new asset is irrelevant. Fund managers will focus on the covariance between the new asset and the existing portfolio to assess whether the new investment is worthwhile.

This holds for other risk measures like CVaR and VaR as well: if you're considering these as proxies for risk, you should also consider the correlation between the new asset's risk and the other risks in the portfolio.

### How Large Does "n" Need to Be for This to Hold?
This holds even with relatively small numbers of assets. Eugene Fama has noted that if a portfolio has around 30 assets, and the weights of each asset are small, the property holds.

### Systematic Risk
To understand systematic risk, let's assume we have "n" assets with equal variance and correlation.

As explained earlier, in this specific case where all assets have the same correlation and variance, as $n$ approaches infinity, the portfolio variance becomes:

${\sigma}_{p}^2\hspace{3pt}{\rightarrow}\hspace{3pt}{\rho}{\sigma}^{2}$

The fraction ${\rho}$ represents the systematic risk of the portfolio, which is the risk that cannot be diversified away by adding more assets. In reality, correlations and variances differ, but the intuition remains:
- Idiosyncratic risk can be eliminated through diversification, and is the diversifiable part of ${\sigma}_{p}^2$.
- Systematic risk cannot be eliminated through diversification.

### Riskless Portfolio
The correlation required to construct a riskless portfolio approaches ${\rho}=0$ as the number of assets grows infinitely. In practice, with a large number of assets, a nearly riskless portfolio can be achieved if ${\rho}=0$.

## Mean-Variance Optimization
In mean-variance optimization, we aim to reduce risk while maintaining high returns. Thus, the optimization involves two variables.

When combining "n" assets, we can create a mean-variance frontier, represented as a "parabola."
A linear combination of points on the mean-variance graph can reach any point on this parabola.

The parabola contains means higher than those of any individual asset due to the ability to short assets with lower returns and go long on assets with higher returns.

A mean-variance investor seeks to be on the upper part of the frontier, where the variance (and volatility) is minimized for each level of mean return.

The mean-variance frontier remains a foundational concept in investment management. It was developed in the 1950s by Harry Markowitz and continues to underpin more advanced, modern methods.

### Notation
In mean-variance frontier notation, ${\mu}$ represents the average returns of each asset, and ${\sum}$ represents the covariance matrix of the assets, which is positive definite—no asset is a linear function of another.

The portfolio return is the inner product of the weight vector and the mean return vector:

${\mu}^{p}=({\omega^{p}})^{\intercal}{\mu}$

For "n" assets, the variance of returns is a quadratic form:

${\sigma}_{p}^{2}=({\omega^{p}})^{\intercal}{\sum}({\omega^{p}})$

To minimize portfolio variance:

${\underset{\omega}{\text{min}}}\hspace{5pt}({\omega^{p}})^{\intercal}{\sum}({\omega^{p}})$

Subject to:

$s.t.\hspace{5pt}({\omega^{p}})^{\intercal}\textbf{1} = 1$

This convex constraint set leads to a straightforward optimization, where $w^{*}$ is characterized by a first-order solution.

We can arrive at any other portfolio by adding an additional constraint for the portfolio's mean:

$s.t.\hspace{5pt}({\omega^{p}})^{\intercal}{\mu} = {\mu}^{p}$

Thus, the full optimization is:

${\underset{\omega}{\text{min}}}\hspace{5pt}({\omega^{p}})^{\intercal}{\sum}{\omega^{p}}$

$s.t.\hspace{5pt}({\omega^{p}})^{\intercal}\textbf{1} = 1$

$s.t.\hspace{5pt}({\omega^{p}})^{\intercal}{\mu} = {\mu}^{p}$

The optimal weights for any level of expected return are a linear combination of the weights for the minimum variance portfolio and the tangency portfolio.

The tangency portfolio weights are:

$w_{unnormalized}^{t}={\sum}^{-1}{\mu}$

We normalize the weights by dividing by the sum of $w_{unnormalized}^{t}$ to get the tangency portfolio weights.

The minimum variance portfolio weights are:

$w_{unnormalized}^{v}={\sum}^{-1}1$

Again, we normalize the weights by dividing by the sum of $w_{unnormalized}^{v}$ to get the minimum variance portfolio weights.

As previously noted, the weights of a portfolio for any level of expected return are:

$w^{*}={\delta}{w}^{t}+(1-{\delta}){w}^{v}$

Therefore, if an investor wants to achieve a higher expected return than the tangency portfolio's return, they should go long on the tangency portfolio with more than 100% of their capital and short the minimum variance portfolio, which mathematically implies ${\delta}>1$.

### The Formula for the Tangency Portfolio
The tangency portfolio allocates more weight to assets that:
1. Have higher mean returns.
2. Have lower volatility (variance).
3. Have lower covariance with other assets.

Points (1) and (2) relate directly to Sharpe ratios: intuitively, the higher an asset's Sharpe ratio, the more you should hold of that asset.

Point (3), however, highlights the importance of covariance. Even an asset with a poor Sharpe ratio can be valuable in a portfolio if it has a low correlation with other assets. This asset may be optimized with a higher weight than assets with higher Sharpe ratios but higher correlations.

### Will Everyone Choose the Same Portfolio in Mean-Variance Optimization?
If a risk-free rate is unavailable, investors will choose different portfolios based on their risk preferences.

However, if a risk-free rate is available, all investors should hold (1) the tangency portfolio and (2) the risk-free rate to create any portfolio with an expected return that maximizes the Sharpe Ratio. If an investor seeks a return greater than the tangency portfolio's expected return, they should go long on the tangency portfolio with more than 100% of their assets and short the risk-free rate. Conversely, if an investor seeks a lower return and lower risk, they should allocate less than 100% to the tangency portfolio and invest the remainder in the risk-free rate.

### Working with the Risk-Free Rate
If the risk-free rate is available, the tangency portfolio becomes even more important. It connects the risk-free rate to the frontier, maximizing the Sharpe ratio, where Sharpe can also be represented as the slope of the line between the two points.

A mean-variance investor will always benefit from allocating part of their capital to the tangency portfolio and part to the risk-free rate. This combination offers the best risk-adjusted expected return. The proportion of capital allocated between the tangency portfolio and the risk-free rate depends on the investor's risk preferences: for higher risk and return, the investor should short the risk-free rate and go long with more than 100% of their capital in the tangency portfolio. For lower risk, the investor should allocate less than 100% to the tangency portfolio and more to the risk-free rate.

On the line between the risk-free rate and the tangency portfolio, all combinations (portfolios) of the two have the same Sharpe ratio, which is the highest achievable Sharpe for a static allocation.

In this context, the minimum variance portfolio and all other portfolios become irrelevant if the risk-free rate is available.

Here, the portfolio weights no longer need to sum to one: if the sum of the tangency portfolio weights is less than 1, we assume the remaining capital is invested in the risk-free rate. If the sum exceeds 1, we assume the investor is shorting the risk-free rate.

Considering the risk-free rate and the tangency portfolio, the relationship between variance and return becomes linear: a 50% increase in portfolio variance, combining the tangency portfolio and the risk-free rate, results in a 50% increase in excess returns.

### Capital Market Line
The Capital Market Line (CML) represents the efficient portion of the mean-variance frontier, given the presence of a risk-free rate.

It shows the risk-return tradeoff available to mean-variance investors and has a slope equivalent to the maximum Sharpe ratio achievable by any portfolio.

### Sharpe Ratio
The Sharpe Ratio is defined as:

$SR({w}^{p})=\frac{{\mu}^{p}-r^{f}}{{\sigma}^{p}}$

It represents the steepness of the line between the risk-free rate and the tangency portfolio.
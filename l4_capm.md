# 4. CAPM (Summary of notes)
The Capital Asset Pricing Model (CAPM) is a model that explains expected returns ($\mathbb{E}[r]$), where the expected excess return of any asset is proportional to the market $\beta$.

Like other factor models, CAPM aims to answer the question: what is the mean expected return of any asset in the market?

$\mathbb{E}[\tilde{r}^i]=\beta^{i, m}\mathbb{E}[\tilde{r}^m]$

Here, $\beta^{i, m}$ can be derived from the following formula because we are dealing with a simple regression:

$\beta^{i, m}=\frac{cov({\tilde{r}^i}, {\tilde{r}^m})}{var({\tilde{r}^m})}$

Therefore:
- The expected return of asset $i$ increases when the correlation with the market is higher.
- The variance of asset $i$ increases.
- Any variance of the asset not explained by the market does not help the asset achieve additional excess return $\mathbb{E}[\tilde{r}^i]$.

Furthermore, since CAPM implies the following:

$\mathbb{E}[\tilde{r}^i]=\beta^{i, m}\mathbb{E}[\tilde{r}^m]$

We can express it as:

$\tilde{r}_t^i=\beta^{i, m}\tilde{r}_t^m+\epsilon_t$

where we also assume that:

$\mathbb{E}[\epsilon]=0$

## What Do We Mean by the Market?
In CAPM, the market refers to the tangency portfolio, which includes every type of asset, not just stocks. This could consist of stocks, bonds, cryptocurrencies, real estate, commodities, etc.

While CAPM works better when all assets are included in the "market portfolio," it is still an imperfect model. However, it is common to use the S&P 500 (or another stock index) as a proxy for the market portfolio. In this course, we are using the S&P 500.

## The Efficient Frontier and Its Relationship with CAPM
For the efficient frontier, we often use historical mean returns to create the frontier. However, this does not always work, as the expected return of a particular asset or asset class may differ from its historical performance.

# Testing a Factor Model
Testing a factor model involves checking whether the linear equation it suggests holds historically. In any factor model, the assumption is that $\mathbb{E}[\epsilon]=0$. If this condition does not hold, the model is invalid.

One way to test the model is to run a regression with an intercept ($\alpha$). For the result to hold, the excess returns regression must yield an $\alpha$ of 0 in the "population size." Since we work with historical returns, which are samples and not true population parameters, $\alpha$ does not need to be exactly zero, but it should be statistically insignificant from zero.

## Test Assets
Test assets should carry multiple types of risks. A diversified portfolio, where the $\epsilon$ from the regression is small, allows us to check if $\alpha$ is present.

For example, test assets can include bundles of assets from various sectors: non-durables, durables, energy, manufacturing, utilities, tech, telecom, retail, etc.

## Why Test the Factor Model on Multiple Assets Instead of Just One?
We test the CAPM (or any other factor model) on multiple assets because the model claims to explain the expected returns of any asset.

We can even use an F-test to check whether all $\alpha$'s are insignificant. It is more challenging to ensure all $\alpha$'s are insignificant than just one.

## Testing Alphas
If the CAPM holds, all assets should lie on a straight line with a positive slope, where the x-axis represents $\beta^{m}$ and the y-axis represents the historical excess return.

This assumption is tested by collecting the $\alpha$'s and $\beta$'s from time-series regressions for each asset. If all $\alpha$'s are collectively zero (i.e., not statistically different from zero), the CAPM holds.

If the assets do not form a straight line (in the plot of $\beta$ vs. $\mathbb{E}[\tilde{r}]$), it means that the $\alpha$'s from the time-series regressions are non-zero. The $\alpha$ for each asset is represented by the vertical distance between the asset's point and the line.

Moreover, for CAPM to hold, the line must pass through the origin (when dealing with excess returns) and have a slope that corresponds to the market asset, where $\beta = 1$. This requirement ensures that assets are not "competing with the risk-free rate."

## What About the R-Squared ($R^2$) When Testing an Asset in Time-Series?
The $R^2$ of a time-series regression is irrelevant in this context. This is because factor models aim to explain expected returns, but the regression uses realized returns. The relevant part for assessing whether the factor model is valid is the $\alpha$, not the $R^2$.

Even if the $R^2$ is 0, the factor model can still hold as long as the asset's historical excess return is zero (i.e., its historical return equals the risk-free rate).

We test the factor model with historical returns because, while CAPM (or any factor model) aims to assess expected returns, we only have access to realized returns.

## Why Test CAPM on a Group of Assets?
We test the CAPM and other factor models on multiple assets because the model claims to explain the expected returns of all assets.

Testing on multiple assets increases the likelihood that at least one $\alpha$ will be significant. Therefore, we test if the $\alpha$'s are significant as a group using an F-test (a joint test) rather than a t-test. This makes it harder for the factor model to "pass the test" and correctly estimate expected returns.

For instance, in CAPM, almost any sample will fail the F-test.

## What Are Alphas in the Cross-Sectional Picture?
In the cross-sectional view, alphas represent the vertical distance between the straight line and the point of Market Beta vs. Historical Excess Returns for each asset. In the strong version of CAPM, this line passes through the origin (x, y = 0, 0) and through the market return, where the market $\beta = 1$.

For CAPM, the vertical distances are often too large to have occurred by chance.

## Risk-Reward Tradeoff in the Strong vs. Regression Version of CAPM
Instead of using the strict version of CAPM, where the line must pass through the origin and market return with $\beta$, we can estimate a regression.

## CAPM and Risk Premium
CAPM states that the risk-premium of any asset is proportional to its market beta:

$\mathbb{E}[\tilde{r}^i]=\beta^{i, m}\lambda_m$

The most straightforward way to estimate the market premium is by using the historical sample:

$\lambda_m=\mathbb{E}[\tilde{r}^m]$

The market risk premium $\lambda_m$ is crucial because it represents the reward for taking on market-related risk.

This is a bold statement: stocks differ in expected return solely based on their relation to $\beta_m$.

We also refer to $\lambda_m$ as the slope of the Security Market Line (SML), where $\beta_m$ is plotted on the x-axis and $\tilde{r}$ on the y-axis.

## Testing the Factor Model as the Result of a Regression
Instead of the strict CAPM version, where the line must go through the origin and the market, we can "loosen up" and use a cross-sectional regression. In this case, the expected excess returns of the assets are the dependent variables, and the $\beta$'s are the independent variables.

The cross-sectional regression is expressed as:

$\mathbb{E}[\tilde{r}^i]=\eta+\beta^{i, m}\lambda_m+\nu^i$

Here, $\beta^{i, m}$ serves as the vector of features, and $\lambda_m$ is the parameter.

The new intercept is called $\eta$, and in this case, $\lambda_m$ is the slope of the regression line.

Generally, CAPM yields a lower $\lambda_m$ than the historical market return, and $\eta$ is often significantly different from zero. Historically, CAPM advocates observe that $\lambda_m$ is much smaller, indicating a lower market risk premium. Furthermore, if $\eta$ is significantly different from zero, it suggests that assets can have excess returns without taking on market risk, thus invalidating CAPM.

The cross-sectional test works even if factors are economic data. However, the time-series test only works for factors that are returns.

## What Should I Worry About in the Cross-Sectional Test if CAPM is True?
If CAPM is true, the primary concern in the cross-sectional test is the $R^2$.

If CAPM holds, $\nu^i$ must be small:

$\mathbb{E}[\tilde{r}^i]=\eta+\beta^{i, m}\lambda_m+\nu^i$

The $R^2$ in the cross-sectional regression tests the essence of CAPM. In the population, CAPM should provide an $R^2$ of 100%, although this can differ in samples due to sample bias.

On the other hand, in time-series regressions, the $R^2$ only tells whether the market is a good hedge for the asset, but it does not address the validity of CAPM (or any other factor model).

The $\eta$ is also important for understanding if the factors are the only way to achieve extra excess returns. If, on average, assets have excess returns different from zero without taking any factor-related risks ($\beta$), it means that the factor model is not perfect.
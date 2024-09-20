# 1. Case Study: The Harvard Management Company and Inflation-Protected Bonds
## Introduction
Jack Meyer proposed a significant change to the Harvard Policy Portfolio, which determined the long-term asset allocation of the Harvard endowment across various asset classes.

The proposition aimed to drastically reduce the allocation to U.S. equities and U.S. nominal bonds, while making a substantial investment (7% of the portfolio) in U.S. Treasury Inflation-Protected Securities (TIPS), which had only been added to the portfolio 12 months earlier.

HWC pursued an active strategy to manage its endowment funds. In 1999, HMC managed 68% of the endowment assets internally.

Over the past 10 years, this active strategy produced a real (inflation-adjusted) return of 11.3% per year after expenses. In comparison, TIPS returned 2.2%, U.S. Treasury bonds returned 5.2%, and U.S. stocks returned 15.8% annually.

## Policy Portfolio
The Policy Portfolio established the long-term allocation of the endowment across various asset classes. The management had the flexibility to make short-term tactical adjustments within predefined minimum and maximum limits without seeking prior Board approval. It also served as a benchmark, utilizing well-known market indexes, to evaluate the performance of the active investment strategies pursued by the managers.

The Policy Portfolio would only change in response to:
1. Changes in the goals or risk tolerance of the university as an institution;
2. Changes in capital market assumptions;
3. The emergence of a new asset class in the market.

## Long-Term Goal
Harvard's long-term goal for the endowment was to distribute 4% to 5% of the endowment annually to the university's schools, while preserving the real value of the endowment and allowing for some real growth.

Additionally, the endowment received an average of 1% annually from gifts.

Therefore, to meet its preservation goal, Harvard's endowment required an average real return of at least 3% to 4% per year. To account for spending growth, the endowment needed 6% to 7% in real returns.

## Allocation
The allocation of the Harvard endowment was based on the mean, variance, and correlation between assets. Historical data and expert assessments were also taken into account.

Ultimately, the mean-variance analysis was used to determine the optimal allocation for each asset class, aiming to minimize portfolio return variance while achieving the expected return.

## Is it Necessary to Add TIPS?
To add TIPS as a new asset class to the Policy Portfolio, conditions (2) or (3) must apply:
2. Changes in capital market assumptions;
3. The appearance of a new asset class in the market.

## TIPS
TIPS are bonds whose principal and coupons adjust with the general price level. The structure of TIPS requires the bond's principal and coupon to change based on the monthly inflation level, as determined by the CPI.

## Asset Allocation with TIPS
TIPS offered real yields ranging from 3.2% to 4.25%, compared to 3% from regular U.S. Treasuries. The team considered TIPS an attractive asset for a diversified portfolio due to:
- Relatively high yields
- Inflation protection characteristics

The team believed a 4% yield was a reasonable estimate for TIPS' expected real return, especially for an institution like Harvard with a long-term investment horizon.

## Mean-Variance Optimization Suggestions
The optimization results indicated that inflation-protected bonds were an attractive asset to include in the portfolio.

Jack Meyer evaluated the asset allocations of other university endowments and decided to recommend the new Policy Portfolio.

# 2. Discussion: The Harvard Management Company and Inflation-Protected Bonds
## Why Is Harvard Optimizing the Buckets Instead of Optimizing the Entire Portfolio?
Handling thousands of assets would result in an unstable optimization due to a covariance matrix with a very small determinant. 

Likewise, splitting the portfolio into layers is not optimal if there is correlation between asset classes. For instance, a U.S. stock manager might hold tech stocks, and an emerging market (EM) stock manager might also hold tech stocks, creating high exposure to the same risk. The two-layer optimization prevents optimal diversification between classes. This only works if there is no correlation between classes, which is rarely the case.

Asset classes often exhibit significant correlations, particularly stock classes. Among the available assets, IEF (U.S. Treasury bonds) was one of the few with low correlation to other asset classes. In other words, even if asset classes are labeled differently, they can behave similarly.

## Correlation Changes and the Covariance Matrix Problem
Mean-variance optimization assumes its inputs are fixed, but in reality, correlations between assets vary significantly between in-sample and out-of-sample data, creating prediction challenges.

When the covariance matrix has a small determinant, the resulting portfolio weights are often extreme because the optimization treats returns, covariances, and variances as certainties. This leads to:
- Outweighing assets with slightly better average returns.
- "Crazy" long positions on one asset and "crazy" short positions on another when correlations are high.

As a result, the optimization ends up magnifying the impact of both useful and noisy data. Out-of-sample results diverge significantly from the in-sample optimal solution.

To mitigate the sensitivity issue in the covariance matrix, one can adopt a Bayesian or machine learning approach, with regularization as a key solution.

## Can TIPS Be Its Own Asset Class?
The Sharpe ratio alone is insufficient to decide whether TIPS should be classified as a separate asset class. Instead, one should consider the correlation and characteristics of the asset.

In the case of TIPS, increasing the expected return can greatly impact the mean-variance optimization. If the expected return is perceived to be higher and significantly improves the Sharpe ratio, it might be reasonable to consider TIPS as a separate asset class.

### Impact of Dropping or Changing TIPS Returns
Removing TIPS from the portfolio has minimal impact on the optimization. However, changing the expected returns of TIPS (to better reflect future expectations) can increase their portfolio weight by around threefold.

This increase is due to the covariance sensitivity. A slight improvement in TIPS returns would increase the portfolio's Sharpe ratio by 10 basis points, a significant enhancement.

## Addressing the Instability in the Covariance Matrix
Regularization is a useful method for addressing instability in the covariance matrix, especially when:
- Many assets are involved in the optimization.
- The matrix has high covariances relative to variances (high asset correlations).

### Optimizing the S&P 500 Securities
In our sample, we performed a mean-variance optimization on the 500 S&P securities and constructed the following strategies:
- Equally weighted
- Parity (volatility-adjusted)
- Traditional mean-variance optimization
- Non-negative weights
- RIDGE regularization
- LASSO regularization

The equal-weighted and parity portfolios showed a 99.7% similarity. The non-negative weights portfolio had an 80.7% correlation with these, indicating that despite the more complex optimization, results remain relatively similar.

Out-of-sample, Sharpe ratios dropped significantly, and equal weights provided the best risk-adjusted excess returns. With hyperparameter tuning, RIDGE and LASSO would likely outperform equal weighting. Even without tuning, they still outperformed traditional mean-variance optimization.

The mean-variance optimization performed worst out-of-sample due to in-sample overfitting, a problem magnified with the 500x500 covariance matrix, which had a far smaller determinant than a simpler 11x11 matrix.

Moreover, the gross leverage of the mean-variance optimizer was 250x, with extreme long and short positions (e.g., 8000% long, 10000% short), and high turnover that would erode returns through trading costs.

### How Did Harvard Manage These Issues in Its Optimization?
The investment committee set constraints on the weights. For instance, an asset could not be shorted or exceed a certain threshold.

In Harvard's case, the mean-variance optimization included additional boundary conditions:

$h_{i}(w)\hspace{3pt}{\leq}\hspace{3pt}d^{max}$

$h_{i}(w)\hspace{3pt}{\geq}\hspace{3pt}d^{min}$

This optimization included two equality constraints and "2n" inequality constraints, making the problem more complex. However, the numerical optimization remained feasible, as it still operated within a convex, linear program.

### The Problem with Setting Bounds
The bounds on weights are largely arbitrary. They introduce additional inequality constraints ("2n"), complicating the optimization.

When performing the optimization, the "cost" of each constraint can be assessed. This helps gauge how far the solution is from the "optimal" due to these a priori or institutional constraints.

To avoid arbitrary constraints, regularization approaches have gained popularity. These methods can bypass the need for constraints entirely.
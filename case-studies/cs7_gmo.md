# 7. Case Study Discussion: GMO

## Why does GMO think they can predict the long run better than the short run?
- GMO focuses on macroeconomic signals, which tend to perform better over the long run.
- Markets can overreact: "it is a beauty contest and it is a weighing machine in the long run." According to GMO, various market frictions or investment sentiment can cause short-term surprises and unexpected events, but in the long run, value will align with fundamentals. They believe their strength lies in predicting the long-term rather than short-term market movements or investor reactions to news.

## How has this approach led to contrarian positions?
In the 1990s, most investors avoided stocks with a high dividend-to-price ratio, as tech stocks dominated the market. GMO, being bearish on tech stocks and eventually the overall market, took a contrarian stance. While they missed out on the rapid rise of tech stocks during the 1990s, they avoided heavy losses during the early 2000s market crash, appearing favorable in hindsight.

## Surviving as a contrarian
Surviving as a contrarian is challenging: the market can remain irrational longer than you can remain liquid. You might either (i) lose too much or (ii) your investors could pull the plug. 

GMO had to be cautious in maintaining their contrarian stance during the 1990s. Career risk is a significant factor in being contrarian. When the market and your portfolio are both down, it’s easier to explain losses to investors, reducing the risk of losing them. However, when you’re a contrarian, your performance can diverge from the overall market, which can create opportunities for investors to leave, especially when the broader market is doing well. Any hedge fund not only aims for good returns but also strives to avoid underperforming when peers are excelling.

A good contrarian investor might be right only 55% of the time, making it difficult to predict the market consistently. There will be periods, even entire years, of underperformance compared to the broader market. Being a contrarian carries higher risk but can also yield higher rewards.

## Why does GMO think the market premium will not be as high in the next 10 years compared to the previous 40-50 years?
GMO does not believe the market returns from the past 40-50 years provide an accurate representation of future returns. Market fundamentals have changed significantly since that period, leading them to expect lower market premiums moving forward.

They observed that the dividend-to-price ratio ($DP$) was already lower, indicating less room for growth.

GMO even forecasted a negative market premium for 2007. In 2011, they revised their bond forecast from 2% to 0% and adjusted their dividend price forecast as well. At the time, they predicted negative excess returns for U.S. equities over a 10-year horizon.

For instance, between 2001 and 2011, market performance lagged behind the risk-free rate, largely due to the dot-com crisis and the 2008 financial crash.

## Analysis of GMWAX compared to SPY
GMWAX and SPY are highly correlated, but GMWAX consistently underperforms compared to SPY. The Sharpe ratio for SPY was 24% during the 1996-2011 period, while GMWAX's Sharpe ratio was only half of that. 

For the period between 2011 and 2021, when the market performed better, GMWAX had a Sharpe ratio of 69%, while SPY’s Sharpe ratio was 117%. The mean return for GMWAX was also much lower.

GMWAX also exhibited worse tail risk compared to SPY. Its kurtosis and skewness were significantly worse. Although GMWAX's CVaR and VaR were better than SPY, when adjusted for return, they were much worse.

Additionally, the Information Ratio for GMWAX was negative, meaning that the Sharpe ratio, excluding market-explained performance, was negative.

## Forecasting
When examining the dividend-to-price ratio ($DP$), earnings-to-price ratio ($EP$), and the U.S. 10-Year Treasury yield (US10Y), the signals are highly correlated. Given this high correlation, predicting long-term horizons yields better results.

We often compare these forecasts to the "naive forecast," which is the historical mean up to that point.

During the 2008 financial crisis, the forecasting using $DP$ and $EP$ differed significantly. The $DP$ spiked due to a sharp decline in prices without a corresponding drop in dividends, while earnings fell more than dividends.

## Strategy
After establishing a weight for a strategy based on the expectation for $r_{t+1}$, one must multiply that weight by $r_{t+1}$ to calculate the actual return.

When suffering from look-ahead bias (using the entire time period to define parameters), the strategy for SPY that performed best was based on $DP$, $EP$, and US10Y. This approach showed superior cumulative returns compared to other strategies, especially when using both $DP$ and $EP$.

However, when forecasting out-of-sample (predicting for the next period based only on data up to a certain point), results were worse. If we fit the regression up to a specific period, predict the next one, allocate, and repeat the process, the outcome differs significantly because look-ahead bias is eliminated. In this scenario, the out-of-sample $R^2$ for forecasts using $DP$, $EP$, and combined variables was negative, indicating that these forecasts performed worse than the naive approach. A positive out-of-sample $R^2$ would suggest better predictions than the sample mean, but that was not the case here. A negative out-of-sample $R^2$ does not necessarily imply that the forecast will result in losses.

For the entire sample, the two best performances came from using all predictors and a SPY passive strategy. SPY Passive was lagging but caught up to the other strategies in recent years. The "All" forecast outperformed consistently throughout the sample period.

## More Complicated Strategies
More complex strategies often show excellent in-sample results but perform poorly out-of-sample.

In-sample, the Tree model significantly outperformed both SPY and the OLS model, and its skewness and Information Ratio (IR) were impressive across all metrics.

However, both the Tree and Neural Network models performed poorly in out-of-sample forecasts.
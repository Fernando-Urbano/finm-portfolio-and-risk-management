# 8. FX Carry Trade
Carry refers to investing in an asset with higher cash flow.

The goal is to highlight where expected returns for currencies are high and where they are low.

FX Carry aligns with the idea of high dividend carry: the simple view that higher cash flow correlates with higher expected returns is generally correct.

We define the FX market as follows:

$S_t$: Represents the foreign exchange rate, expressed as USD per foreign currency. When $S_t$ rises, the dollar weakens as more dollars are required per foreign currency. When $S_t$ falls, the dollar strengthens.

## Return of Foreign Currency
The return on a foreign currency is not just $\frac{S_{t+1}}{S_{t}}$.

This is because when buying a currency, we also gain the foreign currency's interest rate. However, we do not earn the local currency’s interest rate.

Thus, the USD return on holding euros, for example, is defined as:

$\frac{S_{t+1}}{S_{t}}R_{t+1}^{f, euro}$

Where $R_{t+1}^{f, euro}$ is the foreign interest rate of euros.

## Forward Exchange Rate
The forward exchange rate for a one-period FX contract $S_{t+1}$ is denoted as $F_t^s$.

## Log Notation
We also define the log notation as follows:

$s = \ln(S)$

$f^s = \ln(F^s)$

$r_{t, t+1}^{f, currency} = \ln(R_{t, t+1}^{f, currency})$

## Covered Interest Parity (CIP)
Covered Interest Parity describes a closed-form relationship between the spot rate and forward rate: the difference between the forward and spot rate is determined by the difference in risk-free rates.

$f^s_t - s_t = r_{t, t+1}^{f, dollars} - r_{t, t+1}^{f, euros}$

This relationship must always hold; otherwise, arbitrage opportunities would exist.

The forward rate can be replicated using the spot rate. We can move dollars to the future without foreign exchange risk by:
- Depositing into the US Treasury.
- Buying euros today and selling euros forward (locking in with the forward rate).

Both methods of moving dollars through time are risk-free, so they must offer the same returns.

Therefore, the relationship between forward and spot rates is determined by the interest rates of the respective countries.

The only potential exception is counterparty risk.

However, in general, this is a non-arbitrage relationship (law of one price) and not just "a model."

Empirical data supports this relationship, except during periods of extreme market stress (e.g., the 2008 crisis).

It is called "covered" because the position is hedged to remain risk-free.

## Uncovered Interest Parity (UIP)
The expected growth in the foreign exchange rate is equal to the difference in risk-free rates.

$\ln(\mathbb{E}[S_{t+1}]) - s_t = r_{t, t+1}^{f, dollars} - r_{t, t+1}^{f, euros}$

The expected future exchange rate relative to the current rate should be determined by the difference in interest rates.

The logic behind UIP is that if the risk-free rate is higher in one country, money should flow there, causing its currency to appreciate.

According to UIP, the gain from a higher risk-free rate should be offset by the currency's appreciation.

In contrast to CIP, UIP is about expectations rather than realized values. In expectation, these should equalize.

If UIP does not hold, and assuming no credit risk, we could expect money to flow to the currency offering higher returns. However, uncertainty may prevent investors from exploiting this fully.

If UIP holds, holding one currency over another suggests that, on average, returns would be the same. Therefore, if UIP holds, investors do not demand a premium for holding one currency over another. In a world where investors are risk-neutral to currency, UIP would hold, and a naive investor seeking the highest interest rate would make no more than others.

However, the naive investor might still be lucky! Just like with higher dividend stocks, investing in currencies with higher interest rates often leads to higher expected returns. Empirically, UIP does not hold as investors are not risk-neutral to currency risk.

CIP holds and is a no-arbitrage condition, while UIP is a model that attempts to explain the world. Nonetheless, UIP does not perform well in practice, while CIP holds up very well in the data!

If UIP holds, the forward rate would be the best predictor of future prices (i.e., where the spot rate will go). This would only be true if risk-neutral probabilities align with physical probabilities. However, due to investors' aversion to currency risk, these probabilities do not match.

We test UIP by running this regression:

$s_{t+1} - s_t = \alpha + \beta (r_{t, t+1}^{f, dollars} - r_{t, t+1}^{f, euros}) + \epsilon_{t+1}$

If UIP holds, the difference should be explained by the interest rate differential.

Thus, if UIP holds:
- $\beta = 1$: indicating an average equal relationship.
- $\alpha = 0$
- $R^2$ can vary, as this is about expectations, not realized values. For CIP, we would expect a high $R^2$, but for UIP, the focus is on the average relationship.

This regression could also be conducted using the difference between the forward and spot rates.

### What Does Beta ≠ 1 Mean?
If $\beta = 1$, FX rate changes eliminate profits from one side of the trade.

If $\beta < 1$, the difference in interest rates is not fully offset by FX rate changes, making it worthwhile to favor the higher interest rate side on average (in expectation).

However, $\beta < 1$ alone does not guarantee only partial offset. For that, we would also need $R^2$ to approach 100%.

A negative $\beta$ suggests that the interest rate differential and FX change move in the same direction: a negative $\beta$ implies an investor could profit from both the high interest rate and FX changes (FX usually moves in the opposite direction).

If $\beta > 1$, the FX change more than offsets the interest rate differential.

### Predictability Strength?
The regression used to test UIP can also forecast returns. However, strategies based on these forecasts typically do not achieve high Sharpe ratios.

Dynamic strategies often yield results very different from simply holding currencies passively.

## Carry Trade
Carry trade involves taking positions in currencies based on their carry, i.e., the interest rate differential.

Carry trade profits from the fact that UIP generally does not hold.

Carry trades (not limited to currencies) performed exceptionally well from the 1990s to 2007 but faced significant drawdowns during the 2008 financial crisis.

Carry trades offer a premium because investors are not risk-neutral to foreign exchange risk.

The strategy is widely used across asset classes, including currencies, stocks, and bonds, and has shown strong performance and premiums.

Given its longevity, carry is likely driven by more than behavioral factors; there is a systematic aversion to currency risk.

Carry trades tend to exhibit negative skewness. For instance, the "peso problem" is an example: the Mexican peso offered high interest rates and attractive returns, but when the "peg" collapsed, FX volatility led to significant negative skewness in returns.

Excluding periods of high negative skewness, carry trades can show a Sharpe ratio of 1, but this drops significantly when including those problematic periods.

## Risk-Free Rate and FX Change
The risk-free rate and FX rate changes must align in time horizons for comparisons to be valid.

### CIP
Covered Interest Parity (CIP) is a no-arbitrage condition about moving dollars through time. It generally holds well in practice but breaks down during periods of market stress, such as the 2008 crisis.

The forward-spot difference must equal the interest rate differential for the same period.

By locking in the rate, the risk is removed from the trade, ensuring this relationship holds.

### UIP
Uncovered Interest Parity (UIP) is a model suggesting that interest rate differentials should be offset by FX changes.

Unlike CIP, UIP is a model that may or may not work in practice.

The UIP model forecasts FX movements solely based on interest rate differentials. According to UIP, there should be no expected positive or negative premium in currency trades, and betting on a specific currency should not yield extra returns. However, historically, this expectation does not hold well.

This does not mean one cannot make money in foreign currency markets, but it does mean the expectation is for no net gain.

### Carry Trade
The carry trade strategy can be applied to different asset classes. It involves going long on assets with higher yields/dividends and shorting those with lower yields.
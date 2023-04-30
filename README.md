# GARCH-model-forecast

**Introduction:** An exciting part of financial modeling is making predictions!. In this project, I'm going to use GARCH (1,1) model to forecast volatility of S&P500 index (GARCH model is a popular approach to model volatility in financial time series data) <br>

:question::question::question:Why we need to forecast volatility :question::question::question: <br>
:point_right: Because it allow us to estimate the uncertainty of future return. Volatility measure the dispersion of asset's return and as an investor, you definitely want to inform about level of risk before making investment decision.<br>

**Definition of some terms:**
I highly recommend you read it before dive in
- Volatility: a statistical measure of the dispersion of asset returns over time. It's computed as Standard deviation or Variance. In general, the higher the volatility, the riskier a financial asset
- Volatility index (VIX), derived from S&P 500 option prices, is a parameter of the US stock market expected volatility and risk sentiment. It demonstrates "volatility clustering", that is, periods of high or low volatility tend to persist. Large price changes are very likely to be followed by more large changes, and vice versa. Volatility clustering happens because markets tend to respond to new information shocks with dramatic price movement, and it takes time for the shocking effect to resolve and dissipate.
- white noise process contains a sequence of random variables that cannot be predicted. A time series is white noise if the variables are independent and identically distributed with a mean of zero.
- A residual is the difference between the observed value of a variable at time t and its predicted value based on information available prior to time t. If the prediction model is working properly, successive residuals are uncorrelated with each other, that is, they constitute a white noise time series
- The GARCH model parameters omega, alpha, beta are estimated using the "maximum likelihood method". It means: the fitting process tries to find parameter values for which the GARCH model is most likely to have generated the observed time series data

**Revision some important formula:**
Note: 'u' in below formula stand for rate of return and rate of return will be treated as the residuals (eplsilon ε) in a GARCH model - this is a common approach in finance.

![obraz](https://user-images.githubusercontent.com/128978862/234706944-8c9d079f-6e00-4b86-9c24-b77b40c91281.png)
![obraz](https://user-images.githubusercontent.com/128978862/235201621-7e1bd426-73e3-46ab-b48f-713d4a01b6aa.png)


**Note:**
- Since it a time series data, it's important to specify 'Shuffle=False' in split data (the data order won't be messed up when it's splitted)
- You can set update_freq with higher value if your dataset is bigger.
- For practice purpose I still included normal distribution assumption of the standardized residuals in this model. However, the use of its in GARCH models are not representative of the real financial world. Fat tails and skewness are frequently observed in financial return data.

Rolling window forecast - repeadtedly perform model fitting and forecast as time roll forward. In simple words, we have 200 observations of a time-series. First, we estimate the model with the first 100 observations to forecast the data point 101. Then we include observation 101 into the sample, and estimate the model again to forecast the data point 102



Use a hypothesis test to help decide whether to keep or drop a model parameter. Hypothesis test is a statistical way to verify a claim, also known as the "null hypothesis or H0, that is made about a population using the sample data. The alternative hypothesis is the one we would accept if the null hypothesis is concluded to be untrue. As a general rule, the significance level is commonly set to 0.05, meaning that the probability of observing the results in our data by chance is just 5%. Let put it in simple word, we have a coin that we want to test if it's fair or biased. The null hypothesis would be that the coin is fair, meaning it has an equal chance of landing on heads or tails. The alternative hypothesis would be that the coin is biased, meaning it has a higher probability of landing on one side than the other.

To test this, we could flip the coin a certain number of times and count how many times it lands on heads and tails. Then, we could calculate the probability of getting that result if the coin is fair. If the probability is very low (typically, less than 5%), we would reject the null hypothesis and conclude that the coin is biased. If the probability is not low enough, we would fail to reject the null hypothesis and conclude that we don't have enough evidence to say that the coin is biased.

5. P-value

From a statistical significance test, we can obtain the p-value, which is used to compare with the predefined significance level to decide whether to reject or accept the null hypothesis. P-value is the probability value of obtaining the observed results of a test, assuming that the null hypothesis is true. It tells us what the odds are that the results could have happened by chance. The lower the p-value, the more surprising the evidence is, the more ridiculous our null hypothesis looks. In other words, reject the null hypothesis if the p-value is smaller than the specified significance level, such as 5%. 
As a rule of thumb, if the absolute value of the t-statistic is larger than 2, the null hypothesis should be rejected.





Note: Don't confuse rolling window forecast with Moving average. Although both of them are used in GARCH model, Rolling window forecast is a technique used for forecasting, whereas moving averages are used for smoothing and trend identification in time series analysis.
Preference: Financial Engineering in the project development, Prof.Zbigniew Krysiak, Szkoła Główna Handlowa w Warszawie (SGH)

# GARCH-model-forecast

**Introduction:** An exciting part of financial modeling is making predictions!. In this project, I'm going to use rolling window forecast in GARCH model - repeadtedly perform model fitting and forecast as time roll forward. In simple words, we have 200 observations of a time-series. First, we estimate the model with the first 100 observations to forecast the data point 101. Then we include observation 101 into the sample, and estimate the model again to forecast the data point 102.
GARCH is a popular approach to model volatility in financial time series data.

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



You can set update_freq with higher value if your dataset is bigger.
For practice purpose I still included normal distribution assumption of the standardized residuals in this model. However, the use of its in GARCH models are not representative of the real financial world. Fat tails and skewness are frequently observed in financial return data.

Note: Don't confuse rolling window forecast with Moving average. Although both of them are used in GARCH model, Rolling window forecast is a technique used for forecasting, whereas moving averages are used for smoothing and trend identification in time series analysis.
Preference: Financial Engineering in the project development, Prof.Zbigniew Krysiak, Szkoła Główna Handlowa w Warszawie (SGH)

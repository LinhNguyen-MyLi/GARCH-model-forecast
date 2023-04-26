# GARCH-model-forecast

**Introduction:** An exciting part of financial modeling is making predictions!. In this project, I'm going to use rolling window forecast in GARCH model - repeadtedly perform model fitting and forecast as time roll forward. In simple words, we have 200 observations of a time-series. First, we estimate the model with the first 100 observations to forecast the data point 101. Then we include observation 101 into the sample, and estimate the model again to forecast the data point 102.
GARCH is a popular approach to model volatility in financial time series data

**Definition of some terms:**
I highly recommend you read it before dive in
- Volatility: a statistical measure of the dispersion of asset returns over time. It's computed as Standard deviation or Variance. In general, the higher the volatility, the riskier a financial asset
- Volatility index (VIX), derived from S&P 500 option prices, is a parameter of the US stock market expected volatility and risk sentiment. It demonstrates "volatility clustering", that is, periods of high or low volatility tend to persist. Large price changes are very likely to be followed by more large changes, and vice versa. Volatility clustering happens because markets tend to respond to new information shocks with dramatic price movement, and it takes time for the shocking effect to resolve and dissipate.
- white noise process contains a sequence of random variables that cannot be predicted. A time series is white noise if the variables are independent and identically distributed with a mean of zero.
- A residual is the difference between the observed value of a variable at time t and its predicted value based on information available prior to time t. If the prediction model is working properly, successive residuals are uncorrelated with each other, that is, they constitute a white noise time series
![obraz](https://user-images.githubusercontent.com/128978862/234522420-c4147f2f-7816-442b-bd88-e986607082c0.png)

Note: Don't confuse rolling window forecast with Moving average. Although both of them are used in GARCH model, Rolling window forecast is a technique used for forecasting, whereas moving averages are used for smoothing and trend identification in time series analysis.

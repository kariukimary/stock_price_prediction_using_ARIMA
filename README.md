# stock_price_prediction_using_ARIMA
Time Series Forecasting

Time series is a machine learning problem where time is an important component in model prediction. Time series model can be used in both classification and regression problem. In this article I will focus on time series models which are used in a regression problem in predicting the numerical values such as AR,MA,ARMA,ARIMA.

# What is time series models?
Time series models are set of data points that are indexed in time order, where time is the independent variable. common application of time series in a regression problem may include predicting stock prices, revenue, temperature among others.

# Components of time series models
Time series can be broadly be divided into three components

seasonality component(S):
Seasonality can be defined as a pattern that repeat periodically over period of time or a periodic change to the value that follows an identifiable pattern.

2. trend component(T) :

Trend component can be defined as a long term increase or decrease in data. A positive/upward trends indicates that the data increases over time while a negative/downward trend indicates that the data is decreasing over time.

3. irregularity/residual component(I) :

it is a random fluctuation of data that do not follow any pattern, this component can also be referred as noise or unexpected event.

The above components can be obtained by decomposing time series by the help of additive or multiplicative seasonal decomposition.

Additive time series (S+T+I)
multiplicative time series(S*T*I)

# Stationarity of time series data
Time series data can be described as stationary or non-stationary. To train a time series model, the data to be used must be stationary, if not various techniques such as differencing should be used to transform the data. Data is said to be stationary if it has constant mean, variance and standard deviation.


# Techniques to identify stationarity of the data
The question is how do I know whether my data is stationary or not?
There are several ways to quantify the stationarity of the data, the first one is use of adfuller test. This method examines the stationarity of data based on null hypothesis that the data is non-stationary and alternatively hypothesis data is stationary. if the p-value obtained through ADF is less that 0.05 that is 5%, then the data is said to be stationary else its not stationary. The second method is ACF(Autocorrelation function), this methods summarizes correlation between current observations and past observation. Finally, Rolling statistics can also be used to check the stationarity of the data. this method calculates the mean and the variance over a moving window.

# Transforming non-stationary data to stationary form
Another question can be, now that my data is not stationary how do make it stationary? Differencing is one of the way of transforming non-stationary time series data to a stationary form. the code below explains how differencing technique works, Differencing involves subtracting the previous observation (lag) from the current observation in the time series. This process helps remove trends and seasonality, making the data more stationary.

# Time series models 
AutoRegression(AR):
AR is a statistical method that models the relationship between a variable and past observation(lagged values), where number of lagged observations are represented by(p).

2. Moving average(MA):

MA is a method that models the relationship between a variable and a weighted sum of past white noise error terms. It is represented as MA(q), where ‘q’ represents the number of lagged white noise error terms to consider.

3.AutoRegression moving average(ARMA) :

ARMA combines both autoregressive and moving average components to model time series data. It is represented as ARMA(p, q), where ‘p’ and ‘q’ denote the orders of the autoregressive and moving average components, respectively.

4. AutoRegression Integrated Moving Average(ARIMA):

ARIMA is a more comprehensive model that incorporates differencing to make the data stationary before applying AR and MA components. It is represented as ARIMA(p, d, q), where ‘p’ is the autoregressive order, ‘d’ is the differencing order, and ‘q’ is the moving average order.


# ARIMA
Arima model

A moving average model is an auto regressive model. To recap: an auto regressive model is a predictive time series model that believes you can predict the future based on the historical values of that what you want to predict. Suppose you want to predict the popularity score of Trump. An auto regressive model predicts Trump’s popularity based on his popularity of the previous days. A Moving Average (MA) model takes the average of his past popularity. Based on how many days you look in the past and how you combine them together, you get different type of MA’s (weighted moving average).

Mind I gave an explanation of the predictive MA model, not the MA decomposition filter.

First, ARMA is a part of a set of techniques for analyzing data which is sequential, usually with time as an independent variable. (However, I have used the techniques to analyze date where time was not a factor!) Because the data is usually taken sequentially in time at a given interval, the data itself is called a time series. The object of these techniques is to find an equation which explains the data and to make a prediction from the data. These predictions are used in statistics, economics, industrial management and in control systems.

ARMA itself is a combination of two of the techniques: auto regressive (AR) and moving average (MA). First considering the regressive part, this is most simply a linear curve fit to a set of data points. As a new data point comes in, the regression is moved up one point and the oldest data point is dropped out. The length of data points considered is noted as AR(4) where 4 of the latest data points are considered. The coefficients of the regression are weights or parameters of the equation and are usually found using least squares regression.

The moving average part does exactly the same thing except the error between the actual value and the predicted value is used instead of the data points. Thus, MA(3) would be a weighted average of the current error and the last two errors. Again the weights are usually found by subtracting the mean from data point and then using least squares regression to determine the weights.

When these two techniques are put together by addition, the result would be an ARMA(4,3) model.

There are many extensions to these basic AR and MA techniques including an integrating terms for an ARIMA model, using nonlinear terms for a NARMA model, using exogenous variables to form ARX, MAX, ARMAX and NARMAX models. Another set belonging to these techniques are the ARCH and GARCH models ( advanced forms include integral and nonlinear terms as well) which use terms representing statistical measures.

EDIT ADDED: See my comment below on goodness of fit. There is something more about this that I just thought of as I was lying bed. ARMA and other models of this type often are very good at making one step ahead predictions. However, they often fail miserably when making multi step estimates. I think this because the next point is probably bound limited in how much it can vary from the previous point in most cases. But the error in going further is at least additive and may be multiplicative or exponential resulting in the prediction straying further and further from actual collected data. Thus, user beware!



Time series data is different in terms of

Time-based dependency. Observations are not independent of each other but current observation will be dependent on previous observations. Today’s temperature cannot be predicted independently but is dependent on yesterday’s weather conditions.
Trends that can be increasing and decreasing with time along with seasonality trends. Sale of rain jackets increases or decrease year on year depending on how much it rains that year and also have seasonality attached.
The goal of Time Series analysis is

Identify the underlying forces that lead to a particular trend in time series pattern
Predict future values of the time series variable
This will help to identify the patterns from the observed time-series data.

Identifying patterns in time series data
Time series analysis assumes that time-series data consists of some systematic pattern and some random noise

If we remove the random noise then the systematic pattern would be more prominent. This can be done using Time Series Decomposition.

A systematic pattern in time series data can have a Trend or a Seasonality.

The trend in Time Series data can be linear or non-linear that changes over time and does not repeat itself within the known time range. There is repetition in data over systematic intervals of time.

Demand for a stationary product would steadily increase over time along with seasonality attached to the demand. Demand for stationary is very high during the back-to-school month.

Time Series decomposition-

The decomposition of time series is a statistical task that deconstructs a time series into several components. Each component represents one of the underlying categories of patterns.

Types of time series patterns:

Trend(T)- reflects the long-term progression of the series. A trend exists when there is a persistent increasing or decreasing direction in the data. The trend component does not have to be linear
Cyclic ( C)— reflects repeated but non-periodic fluctuations. The duration of these fluctuations is usually of at least two years
Seasonal(S)-reflects seasonality present in the Time Series data, like demand for flip flops, will be highest during the summer season. Seasonality occurs at a fixed period of time could be weekly, monthly, quarterly, etc.
Random(R) -reflects random or irregular influences. This is residual after we have removed all other components from time-series data
Time Series decomposition can be additive or multiplicative

Additive Model

Y= T + S + C + R

Additive decomposition should be used when

The magnitude of seasonal variation around the trend cycle does not vary with the level of time series
Multiplicative Model

Y= T * S * C * R

Multiplicative decomposition should be used when

variation in trend is proportional to the level of time series

Additive Time series decomposition
How do we forecast a time series?

Most of the time series data will be non-stationary but a common assumption in many time series technique is that the data is stationary. Time Series data will have some pattern or behavior over a period of time. If we understand the underlying pattern then we can say with a high probability that the time series will follow the same pattern in the future too

Property of stationary data is that it has

constant mean,
constant variance and
autocorrelation does not change over time.
What is stationary data?
A stationary series is one whose statistical properties like mean, variance and auto-correlation is constant and does not depend on time. A data set that does not exhibit trend or seasonality and fluctuations in data is entirely external.

Stationary data is flat looking series, without trend, constant variance over time, a constant autocorrelation structure over time and no periodic fluctuations based on seasonality.

Using a stationary data set, the model can do prediction based on the fact that mean and variance will remain the same in the future periods

A stationarized series is easy to predict. If we understand the statistical property of the stationarized series then we can easily predict the future. The statistical property of the series will remain the same in future as they have been in the past.

How do we know if the data is stationary?
Visual
Augmented Dickey-Fuller -ADF
Visual


Stationary data with constant mean and Non Stationary data with changing mean

Non Stationary data with high variance

Augmented Dickey-Fuller(ADF)Test

Augmented Dickey-Fuller(ADF) is the most popular statistical method to find if the series is stationary or not. It is also called as Unit Root Test.

Unit Root Test determines how strongly a time series is defined by a trend

H0 - Null hypothesis for ADF test is that time series can be represented by a Unit root, that is not stationary. It means that time series has some time dependent structure.

Ha- Alternate hypothesis is that time series is stationary

ADF test gives us the

test statistics,
p-value and
critical values.
If test statistic > critical value, it implies that the series is not stationary.

or

If p>0.05 then fail to reject the null hypothesis. This means that time series has unit root and is not stationary

If p-value <= 0.05: Reject the null hypothesis , the data does not have a unit root and is stationary

What if the time series data is not stationary?
We can apply the different technique to make the data stationary. This technique helps generate series with constant location and scale

Differencing: calculates the difference between consecutive terms or points in the data. Differencing is performed to get rid of the varying mean.

Differencing
Seasonality Differencing: the difference between an observation and a previous observation from the same season. For e.g.; sale of Chocolates is high during festival season. For seasonality differencing we take the sales of Chocolates last year during festival season and sales this year during festival season
Log transformation or square root or power transformation: helps to stabilize the non-constant variance of a series
How to reducing Random noise from Time Series data?
Smoothing is a statistical technique that can reveal the underlying trend, or seasonality or cyclic pattern present in the time series data. Smoothing data removes random variation and reveals trends and cyclic component

smoothing can be applied using

Averaging
Exponential Smoothing methods assigns exponentially decreasing weights as the observation get older. Recent observations are given higher weights compared to the previous observations
Analyzing Trend in the Time Series
As part of trend analysis, we remove the random noise by apply smoothing. Moving Average is the most common smoothing technique. It could be a simple average or weighted average. The benefit of moving average smoothing is that its results are less biased by outliers.

Monotonous time series data can be approximated by a linear function. For non-monotonous non-linear data, we apply transformations like log transformation, exponential transformation or square root transformations to remove the non-linearity.

Analyzing Seasonality in Time Series
Seasonality is a structured pattern of changes within a year. Understanding of the seasonality of data is useful to make a prediction for any time series data like managing right inventory levels or planning production for the right products.

Seasonality present in Time Series can be identified by

Domain knowledge of time series is helpful to understand structured patterns repeating over year
using a plot of the data.
Obtaining a lagged autocorrelation function.
ANOVA: Analysis of Variance —Used to test two groups to check the difference between them.
Now that we understand the underlying pattern of time series it is time for a prediction. We will explore ARIMA

ARIMA Auto Regression Integrated Moving Average
ARIMA is a statistical analysis model for time series that helps us predict future trends for time series.

It is a form of regression analysis that evaluates the strength of the dependent variable relative to other changing variables.

Non-Seasonal ARIMA: Prediction population of a County for infrastructure planning

Seasonal ARIMA: Predicting demand for different products during different months of a year

ARIMA has three components

Auto Regression: AR(p)
Past values are used in the regression equation for the series Y
Autoregression uses dependent relationship between observation and number of lagged observations
The pattern of growth/decline in the data is accounted for using Autoregression
auto-regressive parameter p specifies the number of lags used in the model
Identification of AR is best done using PACF

Representation for AR(2). c is a constant and e is error term
Integrated: I(d)
Differencing to make time-series data stationary
Rate of change of the growth/decline in the data is accounted
d represents the number of times data have to be “differenced” to produce stationary data
Moving Average: MV(q)
Noise between consecutive time points is accounted for by Moving Averages. The model that uses dependency between an observation and its residual error from a moving average model applied to lagged observations
Represents the error of the model as a combination of previous error terms
q represents the number of preceding or lagged values for the error term that are added or subtracted to Y
Smooth out the noise from the time series
Identification of the MA model is done best by ACF
ARIMA model is expressed as ARIMA(p,d,q). Also referred to as non-seasonal ARIMA model

p= number of lags used in the model

d- degree of differencing

q- No. of error terms to include in the model


ARIMA
SARIMA -Seasonal ARIMA Auto Regression Integrated Moving Average
Seasonal ARIMA models rely on seasonal lags and differences to fit the seasonal pattern.

SARIMA model is represented by SARIMA(p,d,q)x(P,D,Q)

We have three additional terms compared to ARIMA model

P is the number of seasonal autoregressive terms

D is the number of seasonal differences

Q is the number of seasonal moving-average terms

How do we choose the values for p,d and q, and P, D and Q?
we use Auto Correlation Function(ACF) or Partial Auto Correlation function (PACF) to find the values for p,d and q to be used in ARIMA.

Auto Correlation tells us how correlated a time series is to its previous values. It is the correlation between observations of a time series separated by k time units.

Partial autocorrelations measure the strength of relationship with other terms being accounted

We can also use pmdarima(Pyramid ARIMA) library which performs a grid search across multiple combinations of p,d and q and P, D and Q. This is the most effective way to build a good ARIMA or SARIMA model.

pmdarima library compare AIC(Akaike Information Criteria) metric to evaluate the performance of different ARIMA models

In the next article on time series, we will explore time series data set using different models in Python


You can use this as a reference framework for all your projects. You can use this template for the standard steps in a Time Series project, namely:
1. Install packages
2. Load datasets
3. Get an overview of data
4. Handle missing values
5. EDA
6. Find seasonality in the data
7. Decompose the time series
8. Check Stationarity - ADF test
9. ACF_PACF plots
10. Box-cox transformations
11. Train test split
12. ARIMA model
13. SARIMA model
14. SARIMAX model
15. Simple exponential smoothing model
16. Holt winters model
17. Get predictions from the model
18. Model evaluations
19. Train and evaluate models
20. Inverse transform box-cox
21. Save the final model


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

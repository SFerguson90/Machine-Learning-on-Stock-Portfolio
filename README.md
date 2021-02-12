# Machine Learning & Portfolio Analysis

![Robot Photo](RoboThinker.png)

## Background

### Data

 Our data will be pulled from the Alpaca API, using a basic function which takes in a start date, end date, and ticker symbol as parameters. This can be found in the Data_Acquisition file.

### Portfolio

 The portfolio will consist of 5 stocks, which we will try to choose from different sectors. We chose MSFT (Microsoft), AMZN (Amazon),
 BRK.B (Berkshire Hathaway B), XOM (Exxon Mobile), and K (Kellogg's). While the group's objective was to choose a different stock from different sectors, they were chosen at random one at a time from each group member. The two stocks with the closest relation would probably be Microsoft and Amazon, because they both overlap in the technolog sector, even though Amazon's primary business is warehousing and logistics.

### Hypothesis

 Different machine learning models will produce different RMSE, MSE, or evaluation metrics with different levels of performance on stocks of different sectors. We're most interested in finding which models overfit, underfit, and how they perform in general. Further into our coding, we'd like to plot buy and sell points based on over-under trading strategies, similar to that of SMA trading strategies.

### Models

 1) ARMA - Autoregressive Moving Average

 2) ARIMA - Autoregressive Integrated Moving Average 

 3) LSTM RNN - Long Short Term Memory Recurrent Neural Network(s)

 **Loops were also utilized to create Autocorrelation and Partial Autocorrelation graphs for each stock in the porfolio.**
 
#### Linear Regression Forecasting

 The group's main approach was linear regression forecasting. While the proved efficient for ARIMA and ARMA models, including other labels would have improved our RNN. 

#### Classification Forecasting

 Something we could have done better, would have been to impliment classification analysis into our predictive models. To do this, we would have classified each positive or negative return as a 1 or 0, and used a logrithmic function to distinquish between the two.

### Considerations

Putting every stock into a model didn't seem like a correct approach, because the portfolio didn't contain assets from like sectors. Because of this, we created functions which took in DataFrame Series parameters for the user to specify the stock from the original dataframe. This allows the functions to be used on different APIs, which return Pandas Dataframes.

Finding the best hyperparameters for our LSTM RNN model proved difficult. After trying different optimizers, Adam seemed to be the most efficient and appropriate.

Amazon was substituted for Tesla, because Alpaca API was unable to get adjusted closing prices for Tesla. This proved problematic, because Tesla had a stock split of 5-1, which affected the price from $2,000 to $400. While the dollar amount wasn't used, because of it's larger numbers, this would still affect the returns column and resizing of data.
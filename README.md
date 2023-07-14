# APPLE STOCK PRICE PREDICTION

### Data
<br>Data used for this project from https://finance.yahoo.com/quote/AAPL/history/
<br>Data has 2517 entries and 7 columns
<br>Starting Date of dataset: 2013-07-09
<br>Ending Date of dataset:   2023-07-07
<br>Apple stock data in the dataset covers the period from July 9, 2013, to July 7, 2023.
### Visualizing stock price trend
![plot](https://github.com/stepgrig/AAPL-stock-price-prediction/assets/103223897/4ff39651-1860-464f-b599-e5a6bd8f98ed)
<br>It's important to note that Apple's stock price is influenced by various factors, including market conditions, investor sentiment, product releases, financial performance, and broader economic trends. As such, the stock price can fluctuate over shorter time periods due to these factors.
![plot2](https://github.com/stepgrig/AAPL-stock-price-prediction/assets/103223897/5112646c-783e-4640-b757-63ca5c9ed441)
<br>This histogram plot can provide insights into the most frequently occurring prices within a specific period. By examining the distribution of stock prices, we can identify the price points that appeared most frequently and gain an understanding of the market's sentiment during that period.
### Visualizing daily return
![plot3](https://github.com/stepgrig/AAPL-stock-price-prediction/assets/103223897/4357895c-d392-44f5-9f0a-18626e24a5f2)
We are calculating the daily return of the stock price. Each element in the return price in the “return” column represents the percentage change in stock price from the previous day.  This technique is commonly used to analyze the volatility and performance of stocks over time. It allows you to examine how the stock price fluctuates and understand the rate of return for each day based on the previous day's closing price.
### Testing for stationarity
To achieve a **stationary** series, we must first estimate the underlying trend within the dataset. Subsequently, this estimated trend needs to be eliminated from the series. This can be accomplished by employing statistical modeling techniques.
To achieve stationarity in a time series, we can apply various techniques Differencing, Log Transformation, Moving Average or Exponential Smoothing.
### Transformation Process
Taking the **logarithm** of a time series can help stabilize the variance and reduce the impact of extreme values. It is often used when the data exhibits exponential growth or has a varying variance over time.
<br>The **rolling mean**, also known as the moving average, calculates the average value of a window of observations. By applying a rolling mean to the log-transformed series, we can estimate the underlying trend. The rolling mean smooths out short-term fluctuations and highlights the long-term trend in the data.
 <br>![Screenshot (32)](https://github.com/stepgrig/AAPL-stock-price-prediction/assets/103223897/1294d8ee-a3e7-4e3f-889b-703346b36d53)
Counting the rolling mean and subtracting it from a log-transformed time series can be a technique used to remove the trend component from the series. This step aims to eliminate the gradual changes or systematic patterns in the data, resulting in a detrended or stationary series. This is particularly useful when the time series exhibits a clear trend that needs to be removed for further analysis or modeling.
![plot4](https://github.com/stepgrig/AAPL-stock-price-prediction/assets/103223897/7f31e8b4-7a8b-40d7-b9cf-67842f09493c)

<br>Our data is now stationarized 
![Screenshot (33)](https://github.com/stepgrig/AAPL-stock-price-prediction/assets/103223897/a41e7870-21a3-44e7-9171-5f5575255217)
### Splitting Data
We split the series based on a specific time duration. We split the series by using a certain percentage of the data for training and the remaining percentage for testing. This approach ensures that the training and testing sets maintain the temporal order of the data.
Splitting the Data keeping chronoligal order of the values. We don't shuffle. Training set should include all the values from the beginning of the data up to a specific point in time. The rest will be a testing set. We have to decide how to split our training dataset if it is too large the model will fit the trainig set too well and will perform poorly. If it is too small we will not be able to create model accurate. Let's do 80-20.
![plot5](https://github.com/stepgrig/AAPL-stock-price-prediction/assets/103223897/4e0ef371-d459-46b0-931f-a44d850018c3)


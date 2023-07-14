# APPLE STOCK PRICE PREDICTION

Apple, a true tech titan and a global leader in innovation, has consistently amazed us with groundbreaking products and exceptional financial performance. As we navigate the ever-changing landscape of the stock market, understanding the future trajectory of Apple's stock price becomes paramount.
<br>As a brokerage firm, our primary function is to facilitate the buying and selling of financial securities on behalf of our clients. We assist them in opening brokerage accounts. We offer a user-friendly trading platform that enables our clients to execute trades efficiently. As a brokerage firm, we may offer investment advice to our clients. When clients place buy or sell orders, our brokerage firm executes those orders on their behalf. We provide research and analysis on various financial markets, individual stocks.
<br>Predicting stock prices can be helpful in daily trading by providing insights and potential opportunities for traders to make informed decisions
<br>The ARIMA model considers historical stock price data, analyzes trends, seasonality, and patterns to make informed predictions. By examining past prices and their relationships, we can uncover valuable insights into the potential direction of future prices.
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
The autocorrelation function (**ACF**) plot shows the correlation between a time series and its lagged values. It helps identify any significant patterns or dependencies within the time series data.
![Screenshot (35)](https://github.com/stepgrig/AAPL-stock-price-prediction/assets/103223897/13b127c4-1a61-432f-b620-d80a02237b85)
<br>The partial autocorrelation function (**PACF**) plot shows the correlation between a time series and its lagged values, while accounting for the intermediate dependencies caused by other lags.
![Screenshot (36)](https://github.com/stepgrig/AAPL-stock-price-prediction/assets/103223897/a4f93075-7ed2-408d-affe-70ea835ed387)
<br>Plotting the training set and predicted values. By visually comparing the training set values with the predicted values, you can evaluate how well the model fits the training data.
![plot7](https://github.com/stepgrig/AAPL-stock-price-prediction/assets/103223897/af0f89c3-9d2f-460e-b34a-30005817d9bf)
<br>
![plot9](https://github.com/stepgrig/AAPL-stock-price-prediction/assets/103223897/80c409df-e645-490e-a20b-d00eb3922de5)
<br>Predicting stock prices, including Apple's, is a complex task that involves a multitude of factors, including market trends, economic conditions, company performance, investor sentiment, and unforeseen events. 
<br>It's important to remember that stock price predictions are not guaranteed to be accurate, and trading always involves risk. Traders should conduct thorough research, use multiple sources of information, and apply their own judgment and risk management techniques when making trading decisions.

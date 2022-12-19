# Time-Series-Momentum-Strategy
In this strategy, we will use a lookback period of 12 months and a holding period of 1 month.

### 1. Import libraries and Read S&P500 data
First, we will import the necessary libraries and then, we will read the csv file with the S&P500 OHLC data using the 'read_csv' method of pandas.

### 2. Convert daily frequency to monthly frequency
DataFrame.asfreq() function is used to convert timeseries to specified frequency. Here, we use BM to get the last business day of the month.

### 3. Calculate yearly returns
DataFrame.pct_change() is used to calculate the percentage returns of the prices. Since the frequency is monthly we will use 12 as a lookback period to specify percentage change calculation over 12 months.

### 4. Calculate holding period returns
Now, we will calculate the holding period returns which is 1 month.

DataFrame.pct_change() is used to calculate the percentage returns of the prices.

Dataframe.shift() function shift index by desired number of periods. Use 1 to shift the index axis by 1 period backward and -1 for 1 period forward.

### 5. Define strategy logic
To backtest this strategy, we need to generate trading signals. Whenever the yearly returns are greater than 0, we buy; otherwise, we sell. We use where() function from NumPy to do this.

### 6. Calculate Strategy Returns
To calculate strategy returns, multiply future_1_month_returns with positions. Then, we use cumprod() function to calculate cumulative strategy returns.

### 7. Analyse Strategy Performance

#### 7.1 Calculate total/absolute returns
The total returns from strategy 1,372.32%

#### 7.2 Calculate annualised returns
The CAGR from strategy is 11.16%

#### 7.3 Calculate annualised volatility
The annalised volatility from strategy is 14.43%

#### 7.4 Calculate Sharpe ratio
The Sharpe ratio is 0.81

#### 7.5 Calculate maximum drawdown
The maximum drawdown is -33.13%

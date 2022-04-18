# **Challenge_4**

## Risk Return Analysis
---
In this challenge I analyzed data of four fund portfolios (SOROS FUND MANAGEMENT LLC, PAULSON & CO. INC., TIGER GLOBAL MANAGEMENT LLC and	BERKSHIRE HATHAWAY, INC.) and S&P 500 market.


### *Necessary library imports:*
Path,
Pandas, 
NumPy,
Matplotlib. 

### *The Analysis*
Using Pandas and Path, read the csv file, whale_navs, into a Jupyter notebook, where all the analysis needs to take place, and created a DataFrame.

After creating the DataFrame, calculated the daily returns for the the portfolios and the S&P 500 market and drop the NaN values, using the `.pct_change()` and `.dropna()` functions.

Plot the new `risk_return_daily` DataFrame using the `.plot()` function as a line plot and box plot. Since the line plot is the automatic plot that will show, there is no need to specify the kind/type of plot that will be plotted. For the box plot, a parameter was created `kind='box'`. 

To further analyze the data need to calculate the annualized standard deviation and sort the values in ascending order:
```python
risk_return_annual_std = risk_return_daily.std() * np.sqrt(252)
risk_return_annual_std.sort_values()
```
By reviewing the data and then creating a rolling window plot I was able to observe the volatility of each fund portfolio and S&P 500 market as well as the relationship between them.


After creating the sharpe ratio, I was able to distinguish which of the funds risks could have a negative return and which ones positive and highest return. Sharpe ratio was calculated using 
```python
risk_return_sharpe = risk_return_annual_avg / risk_return_annual_std
```
and than plotting a bar plot
```python
risk_return_sharpe.plot.bar(figsize=(12,8), title='Sharpe Ratios for 4 Fund Portfolios & S&P 500')
```
The bar plot provided that Soros Fund and Paulson & Co had negative return, while Tiger Global and Berkhsire Hathaway was positive.

Finally, use the covariance and beta to further analyze the data by having smoother lines to review the data on the plots.





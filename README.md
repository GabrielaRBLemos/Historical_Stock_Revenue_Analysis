# Historical Stock Revenue Analysis

## Overview

This project analyzes historical stock data to provide insights into stock and portfolio performance.

## Features
- Automatically identifies the benchmark market indexes based on the stock's country.
- Calculate daily returns, expected returns, and stock volatility.
- Plot adjusted close prices, cumulative returns and daily returns graphs.
- Calculates portfolio returns
- CSV file containing ticker symbols for benchmark market indexes for several countries.

## Prerequisites

Make sure you have the following Python packages installed:

- `yfinance`
- `pandas`
- `numpy`
- `matplotlib`
- `dateutil`

You can install these packages using pip:

```bash
pip install yfinance pandas numpy matplotlib python-dateutil
```
## How to use
### Stock Data Visualization with `display_stock_data()`

The `display_stock_data()` function allows you to visualize the data for an individual stock over various time periods.
#### Syntax:
```python
display_stock_data(ticker_symbol, period)
```
or

```python
display_stock_data(ticker_symbol, start='YYYY-MM-DD', end='YYYY-MM-DD')
```
#### Parameters:


ticker_symbol: The stock's ticker symbol (e.g., 'AAPL' for Apple, 'GOOGL' for Alphabet).

period: A predefined time period for which to display the data. Possible values include:

- 1d (1 day)
- 5d (5 days)
- 1mo (1 month)
- 3mo (3 months)
- 6mo (6 months)
- 1y (1 year)
- 2y (2 years)
- 5y (5 years)
- 10y (10 years)
- ytd (year to date)
- max (maximum available period)

start (optional): The start date for a custom date range in the format 'YYYY-MM-DD'.

end (optional): The end date for a custom date range in the format 'YYYY-MM-DD'.

#### Examples:

To visualize the data for Samsung Electronics (ticker: '005930.KS') starting from August 4, 2023:

```python
display_stock_data('005930.KS', start='2023-08-04')
```
To visualize the maximum available data for Alphabet Inc. (ticker: 'GOOGL'):

```python
display_stock_data('GOOGL', 'max')

```

#### Notes:

- If you specify a period, it will override any values set for start and end.

- If only start or end is provided, the other will default to cover the available data range.

- The default period is max, the default start is 99 years ago, and the default end is today.

### Portfolio Data Visualization with `display_portfolio_data()`

The display_portfolio_data() function enables you to visualize and analyze the performance of a portfolio.

#### Syntax:

```python
display_portfolio_data(symbol_list, money_invested_list, start_list, end_list=None)
```
#### Parameters:

symbol_list: A list of stock ticker symbols.

money_invested_list: A list of amounts of money invested in each corresponding stock in symbol_list.

start_list: A list of start dates for each stock's data in the format 'YYYY-MM-DD'.

end_list (optional): A list of end dates for each stock's data in the format 'YYYY-MM-DD'. If not provided, the end date will default to today.

#### Notes:

- The end_list parameter is optional. If not provided, each stock's data will be displayed up to the current date.

- Ensure that the lengths of symbol_list, money_invested_list, and start_list are all the same. If end_list is provided, it should match the length of the other lists.

#### Example:

```python
display_portfolio_data(['SPY', 'GOOGL', '005930.KS'],[128.0, 230.0, 175.0],['2023-08-04', '2024-01-18', '2023-12-15'])
```

## License
This project is licensed under the GPL-3.0 license - see the LICENSE file for details.

## Acknowledgements
This project utilizes data from Yahoo Finance via the [yfinance](https://github.com/ranaroussi/yfinance) library.


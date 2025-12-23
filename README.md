###Code Overview: Live Data Rolling Correlation Plot for Two Tickers###
This Python script connects to MetaTrader 5, fetches live data for two specified tickers over the last 60 days, computes a rolling correlation of their percentage returns, and then displays an interactive Plotly chart. The chart's y-axis is scaled to show correlation percentages from -100 to 100, and an annotation box shows only the most recent close values of each ticker (without any timestamp).


##Installation and Imports
#Pip Installations
Ensure the following packages are installed using pip:
MetaTrader5
pandas
plotly

#Command:
pip install MetaTrader5 pandas plotly

#Imports
All necessary libraries are imported at the top of the script:
warnings: to suppress future warnings.
pandas: for data manipulation.
MetaTrader5: for connecting to the trading platform.
datetime: for date range handling.
plotly.graph_objects: for interactive plotting.


##Function Descriptions

1.
initialize_mt5()
#Purpose:
Connects to the MetaTrader 5 terminal and logs into your trading account.
#Manual Intervention:
Update the login credentials (login ID, password, and server) as needed.

2.
fetch_mt5_data(symbol, start_date, end_date, timeframe=mt5.TIMEFRAME_M30)
#Purpose:
Fetches OHLC data for a given ticker between specified start and end dates.
#Manual Intervention:
Adjust the timeframe parameter if needed (default is M30).

3.
plot_rolling_correlation(ticker1, ticker2, window=30)
#Purpose:
Fetches data for two tickers over the last 60 days.
Computes percentage returns and calculates a rolling correlation over a specified window (default is 30).
Scales the correlation values (multiplying by 100) so that the range is -100 to 100.
Plots the rolling correlation using Plotly.
Adds an annotation box showing the last close prices for both tickers (without timestamp).
#Manual Intervention:
Adjust the rolling window size if necessary. The chart's configuration (e.g., y-axis range) can be modified within this function.

4.
Main Execution Block
The script begins by initializing and logging into MetaTrader 5.
The user is prompted to enter the two ticker symbols and an optional rolling window size.
The script then calls the plot_rolling_correlation() function to fetch data, compute the rolling correlation, and display the interactive Plotly chart.


This script is designed to be self-contained and interactive, allowing you to quickly analyze the rolling correlation between two assets using live data from MetaTrader 5.

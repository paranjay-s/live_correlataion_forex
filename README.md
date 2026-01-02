# Live Data Rolling Correlation Plot for Two Tickers

## Project Overview

This project connects to **MetaTrader 5** to fetch **live market data** for two user-selected tickers and analyzes how closely they move together over time.  
It computes a **rolling correlation of percentage returns** over the last 60 days and displays the results using an **interactive Plotly chart**.

The correlation is shown on a scale from **-100 to +100**, and the chart also displays the **latest closing price of both tickers** for quick reference.

---

## Features

- Connects to MetaTrader 5 using live trading data  
- Fetches OHLC data for two tickers  
- Computes percentage returns and rolling correlation  
- Displays an interactive Plotly chart  
- Shows only the most recent close prices (no timestamps)  
- Fully interactive and user-driven  

---

## Installation and Setup

### Required Python Packages

Install the required packages using pip:
pip install MetaTrader5 pandas plotly


## Imports Used

All necessary libraries are imported at the top of the script:

- `warnings` – suppresses future warnings  
- `pandas` – data manipulation and calculations  
- `MetaTrader5` – connection to the MetaTrader 5 terminal  
- `datetime` – handling date ranges  
- `plotly.graph_objects` – interactive plotting  

---

## Function Descriptions

### 1. `initialize_mt5()`

**Purpose**
- Connects to the MetaTrader 5 terminal  
- Logs into the trading account  

**Manual Intervention Required**
- Update login ID, password, and server details inside the function  

---

### 2. `fetch_mt5_data(symbol, start_date, end_date, timeframe=mt5.TIMEFRAME_M30)`

**Purpose**
- Fetches OHLC price data for a given ticker  
- Uses MetaTrader 5 historical data  

**Manual Intervention Required**
- Adjust the timeframe if needed (default is 30-minute candles)  

---

### 3. `plot_rolling_correlation(ticker1, ticker2, window=30)`

**Purpose**
- Fetches data for two tickers over the last 60 days  
- Computes percentage returns  
- Calculates rolling correlation over a chosen window  
- Scales correlation values to range **[-100, 100]**  
- Plots an interactive Plotly chart  
- Displays the latest closing prices for both tickers  

**Manual Intervention Required**
- Adjust rolling window size if needed  
- Modify chart configuration (axis limits, layout) inside the function  

---

## Main Execution Flow

- Initialize and log into MetaTrader 5  
- Prompt the user to enter:
  - Two ticker symbols  
  - Optional rolling window size  
- Fetch live data for both tickers  
- Compute rolling correlation  
- Display the interactive Plotly chart  

---

## Usage

- Run the script and follow the prompts  
- Enter two trading symbols  
- View how their correlation changes over time  

This tool is useful for:
- Pair analysis  
- Risk management  
- Portfolio diversification studies  

---

## Summary

This script provides a **simple and interactive way** to analyze the rolling correlation between two assets using **live market data from MetaTrader 5**.  
It is self-contained, easy to modify, and suitable for quick exploratory analysis.
# Crypto Market Intelligence Dashboard — Real-Time & Historical Insights Using Azure, API, and Power BI

This project was built to help a financial analytics firm monitor cryptocurrency markets in real time while comparing against 30-day historical trends. They needed a single, automated tool to support fast investment decisions, assess volatility, and spot growth opportunities.


## What the stakeholders wanted:

--Monitor real-time performance of their key coins (BTC, ETH, SOL, LINK, ADA, AVAX)
--Evaluate market volatility, all-time highs/lows
--Identify top gainers, high-risk assets, and lowest market caps
--Make faster, data-driven invest.


## Questions addressed in the analysis:

-What are the current prices and how have they changed in the past 24 hours?
-Which coin is the top gainer today?
-Which coin is the most volatile (largest 24H change)?
-Which coin has the lowest market cap right now?
-How far is each coin from its ATH (All-Time High) and ATL (All-Time Low)?
-What are the price trends over the last 30 days?
-What is the total market cap of all coins combined today?

## Process:

### 1)API Data Collection:

-Pulled real-time data from the CoinGecko API
-Wrote Python script to fetch 30 days of history
-Stored real-time and historical JSONs in Azure

### 2)Azure Setup:

-Created Azure SQL database
-Created Blob storage for historical files
-Built pipelines in Azure Data Factory:
	Real-Time Pipeline: CoinGecko API → SQL (daily trigger)
	Historical Pipeline: Blob → SQL (manual or monthly refresh)

### 3)Data Integration

-Mapped all API fields into one SQL table: CryptoMarketData
-ADF Copy Activity with retry and column mapping
-Triggered pipelines for daily auto-refresh

### 4)Power BI Dashboard:

-Connected Power BI to Azure SQL
-Created DAX measures (e.g. current price, 24H changes, ATH/ATL gaps, volatility)
-Built visuals (e.g. Line charts, gauges, cards, slicers, dynamic table)
-Published to Power BI Service
-Setup refresh schedule (hourly/daily)
-Resolved all credential issues


## Key Insights Discovered:

-BTC was the most volatile coin today with the highest market cap
-AVAX had the lowest market cap, while BTC showed the highest current price
-All coins are trading well below their all-time highs
-A simple slicer lets you instantly view any coin’s performance
-Historical trends show sharp mid-month movement across most tokens


## Used skills and Tools:

(Build real business tools from scratch)
(real-time APIs) CoinGecko API==>	Real-time & historical crypto data
(real-time APIs) Python==>	Fetching and formatting historical data
(cloud architecture) Azure Blob==>	Storage for historical JSON files
(cloud architecture) Azure SQL DB==>	Centralized storage for reporting
(cloud architecture) Azure Data Factory==>	Pipelines to move API + Blob data into SQL
(BI & Dashboards) Power BI==>	Dashboarding, DAX, and publishing
(Data Engineering)
(Business Analytics , Problem Solving & Story Telling With DATA)


## Automation
-Real-time data updates every day via ADF pipeline
-Power BI dashboard auto-refreshes daily
-Historical data can be updated monthly or as needed
-Entire process is scalable and cloud-native



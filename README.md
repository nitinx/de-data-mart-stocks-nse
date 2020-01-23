# Data Engineering
## Project: Stock Data Mart

## Project Overview
India's National Stock Exchange (NSE) historical data spanning close to 20 years has been sourced in CSV format. Each stock has a file of its own and there are in excess of 1300 stocks. Additionally, a static file has been provided which maps the stock symbol to the Company. This data is to be processed and populated into Amazon Redshift for analytics. 

### Data
Source data is in CSV format and is in the form of multiple files - each stock file has records for a single stock from 2000 onwards. There are 1386 files in all. Additionally, there is one static file mapping the stock symbol to the company.

Dataset has been obtained from Kaggle (https://www.kaggle.com/abhishekyana/nse-listed-1384-companies-data).

Dataset contains two categories of data:

1. **Stock Data**: 1386 files in CSV format which contains stock prices for 1364 NSE stocks from 2000 onwards. One record/stock for each trading day. In all, there are 3,758,123 records. Columns include Date, Open, Close, High, Low and Volume.
   - `File Count: 1386`

2. **Companies Data**: 1 file in CSV format which maps the Stock Symbol to the Company. Contains 1384 records.
   - `File Count: 1`

### Schema for NSE Stocks
Using the song and log datasets, you'll need to create a star schema optimized for queries on song play analysis. This includes the following tables.

#### Fact Table
1. **stocks** - records in log data associated with song plays i.e. records with page NextSong
   - id, symbol, open, high, low, close, adj_close, volume

#### Dimension Tables
2. **date** - date dimension
   - date, year, quarted, month, week, day
3. **companies** - companies to stock mapping
   - id, symbol, company

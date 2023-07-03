# LSTM Stock Predictor Based on Company Fundamentals
---

# Overview
The goal of the LSTM stock predictor based on company fundamentals is to build a stock predictor LSTM model to predict the movement of the stock market using  the machine learning ML) techniques and the fundamental characteristics of a company

The main functionalities include:
- Fundamental data collection and cleaning
- Stock market data collection and cleaning
- Merging the fundamental data and the stock daily closing price
- Build the lSTM Neural Network model to predict the stock 

# Data preparation and cleaning
## Fundamental data collection
The fundamental dataset is collected using Intrinio (www.intrinio.com) API. Intrinio offers a 7-day free trial API to collect 10 years of a company fundamental data. The API delivers the fundamental data in JSON format.

The raw dataset has 134 features quaterly reports. The raw data is receied in JSON format and converted into a dataframe which is saved as a CSV file for offline access. The data is cleaned to remove zeros and NaN values.

Only the relevant features of the fundamental data are kept. The remaining features are dropped. The following features are kept:

    Date
    Ticker
    Quarterly operating income
    Quartely revenue
    Quartely net income
    Total asset
    Shareholder's equity
    EEPS(Basic) incl. Extraordinary items
    Common Equity
    Common Shares Outstanding
    Dividends per share
    Current assets
    Current liabilities
    Cash & Equivalent
    Recievalbles
    Cost of  Goods Sold
    Inventories
    Account payable
    Long term debt
    Debt in current liabilites
    Liabilities  
    
The original data in quarterly format is converted to daily format by using pandas fill froward function

## Daily stock price collection
The daily historical Apple stock price from 1980 to 2022 is collected using Yahoo finance API. The data is cleaned to reomve NaN and zero values. Only the Close and Volume columns are kept for the prediction. All the remaining columns are dropped from the data

## Merging the daily stock Close and Volume with the features of the fundamental dataset
The stock data and the fundamental dataste are merged into a single dataframe. The two data are mrged such that each row of the merged data contains the information from the same day for bothe dataset. When a specific date is in one of the two dataset but it si not in the other dataset set, it is dropped.

# Building LSTM Model
1. Normalize the data
2. Split the data into traning and test 
3. Standardize the data
4. Build the LSTM model
5. Compile the model
6. Fit the model
7. Evaluate the model on the test data
7. Predict values from test data trained using training data
8. Visualise the Close price predictions

# Packages used
- Pandas
- Numpy
- yfinance
- Intrinio API
- Keras
- Scikit-learn
	
## To run the app:
# Contributors
---
	Bakary Sylla, Yadisa Joiner, Marcus LeGare

# License
---
MIT
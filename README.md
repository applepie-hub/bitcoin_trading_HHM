In this notebook I fit a Hidden Markov Model to the Bitcoin historical price data and then use the model as part of a trading strategy that switches an investment between Bitcoin and cash to try and maximize its final portfolio value.

I'm going to simplify things by working with a single averaged Bitcoin price for each day. Initially I will assume that it is always possible to buy and sell as much as I want at a particular day's price with no fees (frictionless market) and later on I will explore the effect of market friction. I will assume that there is zero interest accumulated on the cash but this would be simple to modify.

##Data collection
This involves collecting data for the study, which we performed by following the steps mentioned below :

Finding Bitcoin data sets that fit our study by searching via online datasets from various websites such as finance.yahoo.com, coinmarketcap.com, coingecko.com, gemini.com, and kaggle.com. Thousands of rows were used to determine the size of datasets.
Manually verifying that the columns in the dataset have all of the information necessary to make our research a success; our criterion was at least 5 columns. Finally, we choose a bitcoin dataset containing historical data of bitcoin exchanges recorded every hour interval from gemini.com that fits our research problem well. There are 46390 rows in this dataset, with 7 columns: date, open, high, low, closing, volume BTC, and volume USD. Also, it has data records which start from 2017-01-01 00:00:00 to 2022-04-18 00:00:00 open, high, low, closing, volume BTC and volume USD for a particular hour.

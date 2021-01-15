# Notes-AIForTrading-Udacity

## Project 1: Momentum based trading
**Key Concepts**:
- OHLC chart is interesting for resampled data when tick data intends to be condensed.
- t-test defines the statistical significance of the hypothesis. Can be used when we define our positions and determine the return.
- corporate actions like stock split or reverse split affect the stock prices. As a reason AMZN data looks so condensed.
- signals generated should be backtested on a portfolio and the data should be hypothesized. 
   - the signals are generated on the previous data
   - they are validated using backtested data
   - they should be applied to lookahead data for final validation
   - strategy can be live then.

**Important links**
- Momentum trading: https://www.investopedia.com/trading/introduction-to-momentum-trading/
- Pandas is faster with vectorization. Dont use for loop on the rows as its the slowest thing possible: https://engineering.upside.com/a-beginners-guide-to-optimizing-pandas-code-for-speed-c09ef2c6a4d6

**Few ideas**
- Market sentiment for a ticker is probably a more interesting signal for momentum trading compared to top performing and bottom performing.

-----

## Project 2: Breakout strategy
**Key Concepts**
- **Quant Workflow** 

A typical quant workflow looks like as follows:
```
Universe Selection(Data) ----> Alpha strategy ---> Alpha testing(Alpha stacking)--
         |                                                                 |
         |----------> Risk Modeling -------> Portfolio construction <-------
                                       |
Objective function/Constraints ---------
```

The first step for quants is to analyse the data. The data is often unclean and contain some outliers or anamolies. 

- **Outliers**
   - Anamolies in the data occur either due to human error or some systematic error.
      - Human errors: 
         - Japanese hedge fund employee fat fingered a trade for 610000 for 6 stocks 
      - Systematic error:
         - Discontinuity in data. Like brokerage hitting upper circuit. Stock trading hitting the upper circuit.
   - Spotting outliers in the data
      - Apply a threshold for rise/dip in the data. Can yield to false positives. If coupled with volume might give better yields.
   - Handling outliers in the data
      - Take a secondary source and fill the data using the secondary source.
      - In case of a lack of secondary source, fill the data using the surrounding data. Has a potential of ***Lookahead bias*** and can cause concerns with the data. Works well while researching, but should be skipped for generating trading signal.
   - Spotting outliers in the returns
      - Returns should follow a normalized distribution as much possible. However if they dont, you can check using qq plot.
   - Handling outliers in the returns
      - Use rolling means of returns which will smoothen out the returns. 
      - For a portfolio, you can use the average of the returns for calculating the returns too.
   

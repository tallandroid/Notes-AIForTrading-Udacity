# Notes-AIForTrading-Udacity

### Project 1: Momentum based trading
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

# Recurrent-Network-for-Stock-Predictions 
### The project aims to use recurrent network to predict for future stock prices (next 10 days). 

*   The recurrent network was trained on 24 different stocks in the DOW Index, validates on 2 stocks (implemented to monitors the early stop loss) ,and tests the performance of 2 stocks. 
*   The recurrent network was also trained on over 2000 days and used to predict the stock price of the next ten days 
*   The input feature  is : 
    - Volume of the stock at time (t)
    - Closing Price of the stock at time (t)
*   The output feature: 
    - Closing price of the stock from time (t) to time (t+10)
* Hypothesis : 
  - Man features can contributes to the movement of stock price (such as fundamentals data, market sector, news semantics,mangement change, politics, economy indicators, etc). 
  - However, given that DOW stocks share similar market cap, I hypothesize that there are underlying common trends between a stock's historical price/volume and the next 10 day prices that a ML algorithm can learn. 
  - This hypothesis is driven by the intuition that many investors trade stocks based on "Technical Indicators" ( such as RSI, MA, etc), which is based on the stock's price and volume. The reaction to the stock's historical price and volume should be projected in the future stock price, and is what the recurrent network aims to learn. 

* Future Work : 
  - In the future, I will incorporate additional features including fundamentals data, market sector, and economy indicators to improve data. 

### Author: Xun Xun Shi 

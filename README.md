# Recurrent-Network-for-Stock-Predictions 
## The project aims to use recurrent network to predict for future stock prices (next 10 days). 
### Data 
* Data was aggregated using  yahoo finance API for 27 different stocks in the DOW Index. 
* The recurrent network was trained on 24 different stocks in the DOW Index, validates on 2 stocks (implemented to monitors the early stop loss) ,and tests the performance of 2 stocks. 
### Model Building 
*  Min/Max Standardization was applied to the data 
*  A deep recurrent network was also trained on 2087 days (Note that this number can change depending on when this script is run) and used to predict the stock price of the next ten days 
*   The input feature is : 
    - Volume of the stock at  day 0 - day2087 (t)
    - Closing Price of the stock at day 0 - day2087 (t)
*   The output feature: 
    - Closing price of the stock from day 2087(t) to day 2097(t+10)

###  Hypothesis : 
  - Man features can contributes to the movement of stock price (such as fundamentals data, market sector, news semantics,mangement change, politics, economy indicators, etc). 
  - However, given that DOW stocks share similar market cap, I hypothesize that there are underlying common trends between a stock's historical price/volume and the next 10 day prices that a ML algorithm can learn. 
  - This hypothesis is driven by the intuition that many investors trade stocks based on "Technical Indicators" ( such as RSI, MA, etc), which is based on the stock's price and volume. The reaction to the stock's historical price and volume should be projected in the future stock price, and is what the recurrent network aims to learn. 

###  Testset Result: 
* The trained network is used to predict the next ten days of stock price from the test set.
* For both stocks of the test set, the predicted stock price are lower than the actual stock price, but they follows similar trends between the day t to t+10.
* The 10 day prediction trend ( from t+1 to t+10) was similar to the actual trend in both stocks.
* However, there is a sharp drop in the predicted stock price on day t+1, which is suprising. This sudden drop in stock price could be because the overall DOW stocks dropped during those times that affected prediction, and if these trends also carried out in the validation data then this may contribute to some overfitting of trends.
 ![image](https://user-images.githubusercontent.com/29676594/115327320-b921df00-a15c-11eb-8dea-679305bb5b8f.png)
![image](https://user-images.githubusercontent.com/29676594/115327338-c17a1a00-a15c-11eb-8094-ebd6dd0610d4.png)
 

### Conclusions: 

* As a whole, 25 instances (stocks) with two input features may not be enough to generalize the stock trends. This experiment can be replicated again with higher batches and additional features.

### Future Work : 
* Retrain the RNN with more instances from similar sectors such as from NASDAQ
* Additional Features :
* - Average market performance (such as historical index fund prices)
* - Balance sheet data (Asset, Liabilities,etc) and Income statment data ( Earnings, P/E, etc)
*  - Sector Data ( categorical )

### Author: Xun Xun Shi 

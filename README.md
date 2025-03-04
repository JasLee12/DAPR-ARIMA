# Prediction of stablecoins value
This repository contains my part of a project with DAC in 2022-2023. 

## Objective
The objective of the project is to test the possibility of using ARIMA to consistently predict the future DAPR values in stablecoins liquidity pools.

## Background
Yield farming is the process of providing liquidity to DeFi protocols such as liquidity pools, borrowing and lending services. This has the potential to yield lucrative returns through high return rates, however it is also very volatile and unpredictable. As such, it is one of the common ways people earn or lose money in crytocurrency, including stablecoins. Our focus was on liquidity pools. 

## Approach
### Data source
To start, we needed to obtain data containing historical DAPR values of liquidity pools. For that, we found a website (https://yieldsamurai.com/) that compiles and hosts historical data of various liquidity pools within various protocols. 
### Web scraping
At first, we tried using the common webscraping methods of BeautifulSoup and Selenium. But it was very unsuccessful despite much attemptsPrio and research. Then we had a breakthrough by using Python's request library and successfully obtained csv files of liquidity pools.

![image](https://github.com/user-attachments/assets/4e8bdf2d-f7c4-46fc-a471-31882ec76c6c)

### Analysis
The dataset assigned was on the liquidity pool Uniswap and the stablecoins of USDC and WETH. Since we want to forecast DAPR values, the most ideal algorithm would be a times series model. And we are only interested in DAPR values against time, so this will be a univariate time series.
### ARIMA model
The ARIMA time series was a commonly used one and also the one taught to us previously. A rolling forecast was used to ensure the model predicts only 1 time period ahead as a way to increase accuracy. Train and test sets were created as per usual steps.
The model did not perform as well as anticipated, the accuracy on test data was very bad.

![image](https://github.com/user-attachments/assets/1a2c11d5-67c3-4e04-ace2-50a9888958ff)

### Conclusion
We had similar results with the rest of the team. As such, we concluded that in the case of liquidity pools, the volatility of its nature does not lend itself well to predictions using simple time series analysis on just DAPR values and time.

### Future Considerations
1. Perhaps we could consider enhancing our models, accounting for the extremely volatile nature of liquidity pools, by using models such as GARCH to estimate volatility.
2. Prior to this project, none of us have much experience or interaction with cryptocurrency and liquidity pools. We had a short crashcourse and research to help but it is difficult without domain knowledge. As such, our approach of a univariate time series is likely the wrong direction. We should consider what factors could influence DAPR values and take them into account, it could possibly contribute to a higher prediction accuracy. 

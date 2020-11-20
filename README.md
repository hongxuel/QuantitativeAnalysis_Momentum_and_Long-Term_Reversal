# QuantitativeAnalysis_Momentum_and_Long-Term_Reversal

In this quantitative analysis, I want to test if badly performing stocks in momentum work well in long-term reversal.
***
## Introduction
**1. Motivation**  
&emsp;According to J. Conrad and M. D. Yavuz (2016), short-term momentum and long-run reversal naturally have no connection. Although momentum and reversal are separate and distinct, I am curious about whether stocks performing poorly in short-term momentum strategy will perform well in long-term reversal strategy.  
**2. Data acquisition and process**   
&emsp;I apply historical stock lists of S&P 500 to obtain monthly price and return data (1965-2018) of S&P 500 component stocks from Wharton Research Data Services. Also, I download financial data (1971-2018) of the lastest stocks listed on Nasdaq (on 2020/11/18) from Wharton Research Data Services.  
&emsp;S&P 500 index (1965-2018) and Nasdaq index (1971-2018) are used as benchmarks in the strategy. I use 3-month treasury rates as risk-free rate.  
## Main Strategy  
**1. Strategy Description**   
&emsp;I apply momentum strategy to the first 5-year historical data to select 80% less volatile out of the 20% worst performing stocks as the stock pool for the following reversal strategy. The stock pool is rebalanced every 10 years. I believe that after considering factors including quality, accounting issue, and stock price volatility, stocks which still perform badly in momentum reveal that historical upward trend cannot provide investors with confidence that they will still go up in the next period. Therefore, investors may think these stocks as "easy to reverse path" stocks. Therefore, a reversal strategy may work on this kind of stocks.  
**2. Momentum Strategy**    
&emsp;Momentum strategy is used to select stocks for reversal strategy.  
&emsp;For each component stock, when the 6-month moving average return is greater than its 12-month one, long for one month, otherwise, short for one month.The portfolio is rebalanced at the end of each month.   
&emsp;The second step is to calculate and quintile monthly returns, Sharpe ratios, price volatility and return volatility of the stocks. The first two as an indicator of performance of the stocks in the momentum and the last two as an indicator of the stock quality to screen the stocks.  
&emsp;The third step is to select relevant stocks based on the performance of 5-year momentum strategy for the following reversal strategy investment. I select four kinds of stocks for research: 20% lowest Sharpe Ratio and 80% lowest Price volatility, 20% lowest Sharpe Ratio and 80% lowest Return volatility, 20% lowest Mean return and 80% lowest price volatility, 20% lowest Mean Return and 80% lowest Return Volatility.    
**3. Reversal Strategy**    
&emsp;I use reversal strategy to invest and back-test the portfolio return. Firstly, for those selected stocks from momentum, short if the rolling 12-month return is higher than average past 12-month return of all stocks selected; long it if the past 12-month return is lower. As for weight, for stocks in long position, I use the ratio of the difference between rolling 12-month moving average return and the mean of all 12-month moving average return to the sum of absolute difference between them, and vice versa.  
&emsp;Secondly, I calculate the annualized return, annualized volatility, annualized Sharpe ratio and maximum drawdown to show the performance of this strategy. Then, the value of each kind of portfolio starting from $1 is plotted on the same figure of benchmark to visualize the performance. I also subplot pre-2000 and post-2000 to show the return of the strategy during different periods.     
## Result Analysis    
&emsp;“Protfoliobypp” refers to the 5-year momentum portfolio sorted by stocks with 20% lowest average monthly return excluding highest 20% price volatility.  
&emsp;“Portfoliobypr” refers to the 5-year momentum portfolio with lowest 20% average monthly return excluding highest 20% return volatility.   
&emsp;“Portfoliobysp” refers to the portfolio which has lowest 20% Sharpe ratio excluding highest 20% price volatility.    
&emsp;“Portfoliobysr” refers to the portfolio which has 20% lowest return of individual stock excluding excluding highest 20% return volatility.  
&emsp;Then I compare and plot these portfolios’ performance with benchmark in one figure.    
## Test    
&emsp;(a) I try to revise the momentum strategy to see the difference between the portfolio performances. I use the top 20% best performing stocks in S&P 500 to implement reversal strategy.  
&emsp;(b) I implement the whole strategy in Nasdaq stocks to see the performance.  
## Conclusion   
&emsp;With stocks in the S&P 500 from 1965 to 2018, the strategy has overall good profits with a high mean return and sharpe ratio compared with the benchmark. I select four kinds of stocks as portfolio from momentum to quantify bad momentum performance and find out, though strategies differ from each other, they still gain profits steadily and avoid loss in some bearish market. Among these four portfolios, the "Portfoliobysp" which is constructed by stocks with 20% least sharpe ratio excluding highest 20% price volatility has the highest annualized return at 17.40% and the highest annualized sharpe ratio at 0.37.  
&emsp;Compared with stocks which perform well in momentum, badly performing stocks have higher annualized return and sharpe ratio, which proves that bad short-term momentum performing stock is likely to work well in long-term reversal.  
&emsp;I also find that this strategy cannot be applied to stocks listed on Nasdaq partly because the number of Nasdaq stocks is not sufficient to hold diverification for this strategy. Besides, statistically high volatility and inconsistency prove that this strategy is not suitable for Nasdaq.

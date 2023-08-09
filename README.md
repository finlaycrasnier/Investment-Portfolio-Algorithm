# Investment-Portfolio-Algorithm
An investment portfolio algorithm that combines my personal investment philosophy and skills learned from completing the Udemy course "Algorithmic Stock Trading and Equity Investing with Python".

*This is not to be used as investment advice - this is simply a written piece to gather my own thoughts and have fun practicing some programming.*

## Introduction

Whilst I have designed other smaller algorithms whilst following the Udemy course, I cannot envision myself ever utilising them myself. The aim of this algorithm is to test all the financial, programming and 'soft' skills I have learned, whilst simulataneously creating something myself or others can utilise.

## Investment Strategy

My investment beliefs lie in low-risk long-only holding strategies. I believe most people do not have the skills, time or mental capacity to beat the market on a consistent basis with public investing, and should instead invest in index funds over a long time period utilising DCA. I have full faith in people being able to beat a market, but only if they commit a significant amount of time or resources (of which most working class people do not have) OR have exclusive market knowledge. In this regard, I believe trying to beat the market should be left to professional investors / traders / financial engineers. Generally, this results in average returns of somewhere between 5-10% annually (S&P500), which is still quite impressive, but not enough to make you a millionaire over a short time frame. After reading [this](https://80000hours.org/2015/10/common-investing-mistakes-in-the-effective-altruism-community/) post by Benjamin Todd (founder of 80,000 hours), I was inspired to try something different.

His strategy is an altered version of the classic 'S&P500 until you retire' strategy. It essentially copies the global market portfolio (GMP for future reference), resulting in incredibly low volatility returns. It makes sense from a macro view - technically as long as global GDP improves (which it has been for the last millenia), returns will be positive. The portfolio is based on the idea that the financial markets are driven by four main factors: inflation, deflation, economic growth, and economic decline. Therefore, to achieve consistent returns in any market environment, it is believed that it is necessary to diversify across asset classes that would perform well under each of these conditions. This reduced risk makes leverage much more appealing, allowing decent household returns of around 10-15%. Some figures from the blog (between 1973 and 2013):

Strategy | Returns | Volatility | Max Drawdown
--- | --- | --- | --- 
S&P500 | 10.2% | 15.6% | -51% 
GMP | 9.9% | 8% | -27% 

As we can see, although returns are slightly lower, the reduced voltatility means using a 2x leverage would result in significantly higher returns. Of course, 2013 was a long time ago and a lot has changed in the economic landscape. I will find out how much the strategy has been affected by the time the algorithm is finished, but I suspect the GMP will have performed significantly worse considering the equity boom around 2020/2021.

I aim to modify the strategy as follows:

* Use optimization to calculate appropriate levels of leverage

* Create an input system that will factor in the users personal situations (as noted in the blog) e.g. working in tech --> reduce exposure to tech, own a property --> reduce exposure in property

* Replicate the overall approach to individual assets e.g. US tech equities will only represent their portion of the overall equity market

* Utilise equity valuations (such as P/E ratios) to choose appropriate stocks

Other than these modifications, I will simply be trying to implement and backtest the strategy using Python.

## Strategy Execution

I started with the backtester. I thought it would be the most interesting, and I was also having problems connecting to IKBR, making trading impossible. I came across a few programming / calculation errors, notably calculating the portfolio variance, but after re-visiting the course and reading more online, I was able to fix these fairly quickly.

### Backtester

One major challenge I encountered was correctly documenting the programming. I struggled envisioning it from a spectator point of view, and therefore appropriately commenting / documenting when relevent, and naming variable in a concise, yet easy to understand manor. Whilst this does not affect performance, I found that it is something that I definetly should be improving, especially when working in a team environment. I'm hoping to follow more Udemy courses to get a feel for how 

Another slight problem was the availbility of data from yfinance. Some of the ETFs used in the portfolio were fairly new, and therefore do not have a long pricing history. This meant to calculate accurate returns for the entire portfolio, I had to limit the backtesting to 9 years. Whilst this is unfortunate, as it doesn't truly represent a long-term horizon, it turned out to be happy accident. Seeing how the predictions in the initial blog post panned out, and how the pandemic and recession affected each portfolio was interesting to say the least. 

### Trader

The only short setback I had was the rebalancing. I initially complete forgot about it, and hence, had to amend the code once finished. One thing I would like to improve (technically this is also related to the backtester) is the GMP weighting. Currently, they are pulled as flat figures. I would like to find a resource that continually measures (or at least approximates) the weighting of the GMP, so I can directly link it once and for all.

## Conclusion

When backtesting the portfolio with data from the last 9 years, I got the following results:

Strategy | Returns | Volatility | Sharpe | Max Drawdown
--- | --- | --- | --- | ---
S&P500 | 9.6% | 18% | 0.334 | -33%
GMP | 4% | 8% | 0.0726 | -22%

Whilst the GMP still performed strongly, it isn't as appealing as initially thought, especially if utilising leverage. It barely outperformed UK inflation. Having said that, bond returns have been incredibly weak relative to stocks, which is probably not indicative of the future. Additionally, there have been huge swan events that could be attributed to the large gap between equities and other asset classes. 

It will be interesting to see how the GMP shapes up with increasing focus on decentralised currencies. Perhaps as this market segment expands, returns will increase.

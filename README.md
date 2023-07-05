# Investment-Portfolio-Algorithm
An investment portfolio algorithm that combines my personal investment philosophy and skills learned from completing the Udemy course "Algorithmic Stock Trading and Equity Investing with Python".

*This is not to be used as investment advice - this is simply a written piece to gather my own thoughts and have fun practicing some skills.*

## Introduction

Whilst I have designed other smaller algorithms whilst following the Udemy course, I cannot envision myself ever utilising them myself. The aim of this algorithm is to test all the financial, programming and 'soft' skills I have learned, whilst simulataneously creating something myself or others can utilise.

## Investment Strategy

My investment beliefs lie in low-risk long-only holding strategies. I believe most people do not have the skills, time or mental capacity to beat the market on a consistent basis with public investing, and should instead invest in index funds over a long time period utilising DCA. I have full faith in people being able to beat a market, but only if they commit a significant amount of time or resources (of which most working class people do not have) OR have exclusive market knowledge. In this regard, I believe trying to beat the market should be left to professional investors / traders / financial engineers. Generally, this results in average returns of somewhere between 5-10% annually (S&P500), which is still quite impressive, but not enough to make you a millionaire over a short time frame. After reading [this](https://80000hours.org/2015/10/common-investing-mistakes-in-the-effective-altruism-community/) post by Benjamin Todd (founder of 80,000 hours), I was inspired to try something different.

His strategy is an altered version of the classic 'S&P500 until you retire' strategy. It essentially copies the global market portfolio (GMP for future reference), resulting in incredibly low volatility returns. It makes sense from a macro view - technically as long as global GDP improves (which it has been for the last millenia), returns will be positive. This reduced risk makes leverage much more appealing, allowing decent household returns of around 10-15%. Some figures from the blog (between 1973 and 2013):

Strategy | #Returns | #Volatility | #Max Drawdown
--- | --- | --- | --- 
S&P500 | 9.9% | 15.6% | -51% 
GMP | 10.2% | 8% | 290 | -27%

As we can see, although returns are slightly lower, the reduced voltatility means using a 2x leverage would result in significantly higher returns. Of course, 2013 was a long time ago and a lot has changed in the economic landscape. I will find out how much the strategy has been affected by the time the algorithm is finished, but I suspect the GMP will have performed significantly worse considering the equity boom around 2020/2021.

I aim to modify the strategy as follows:

* Use optimization to calculate appropriate levels of leverage

* Create an input system that will factor in the users personal situations (as noted in the blog) e.g. working in tech --> reduce exposure to tech, own a property --> reduce exposure in property

* Replicate the overall approach to individual assets e.g. US tech equities will only represent their portion of the overall equity market

Other than these modifications, I will simply be trying to implement the strategy using Python.

## Strategy Execution

- No fundamental influencers are included; a stock may rapidly rise because of overwhelmingly positive financial reports or media coverage. These stocks may not revert to their average value.
- No purchase variance between the most significant outlier stocks VS standard outlier stocks
- Overall market picture is not viewed / lack of safety net; index could be rapidly growing and we will continue to short stocks

## Conclusion

- No fundamental influencers are included; a stock may rapidly rise because of overwhelmingly positive financial reports or media coverage. These stocks may not revert to their average value.
- No purchase variance between the most significant outlier stocks VS standard outlier stocks
- Overall market picture is not viewed / lack of safety net; index could be rapidly growing and we will continue to short stocks

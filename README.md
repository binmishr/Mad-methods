# Mad-methods

The details of the codeset and plots are included in the attached Adobe Acrobat reader (.pdf) file in this repository. 
You need to download the same to view the contents. There are referrals to other contents in BLUE colour also to follow.

Before we make these comparisons, we want to remind readers that we’re now including a python version of the code we use to produce our analyses and graphs. Let us know if you find this useful. Second, let’s remind ourselves why we’re analyzing these return expectations methods in the first place, Recall, to construct a satisfactory portfolio one needs estimates of both return and risk for the various assets that merit inclusion. Once you have those estimates, you can use them to combine assets in numerous ways to generate a bunch of portfolios with different risk-return combinations. Hopefully, some of these combinations will fit your required risk/return criteria.

Our project, then, has been to introduce these different methods so that we can ultimately decide which one seems the most useful to help make portfolio allocation decisions. Importantly, we should define the criteria for how we’re going to assess these methods. In the prior posts, we examined the methods’ ability to forecast future returns using the error rate as the main judge. When we actually get down to deciding on our asset allocation, we’re not going to be as concerned with having the best estimate of future returns. Rather, we’re looking to identify portfolios that offer the best risk-adjusted returns based on our estimates. This might seem like too fine of a point. But it is important to note that, assuming we’re trying to build a reasonably diversified portfolio, the accuracy of any individual return estimate will be dampened by the number of assets in the portfolio. Thus we don’t need “perfect” estimates to create a “good” portfolio.

In any case, here’s the plan for this post. We’ll start off exploring the different methods graphically. Then we’ll run the basic models over different time frames. Then we’ll consider whether pooling the predictions can improve results.

Before we begin, it’s important to flag some of the methodological hurdles this analysis faces. We’re using data for the S&P 500, US nominal GDP, and the market risk premium, as published by Dartmouth professor Kenneth R. French. Additionally, the discounted cash flow (DCF) model we analyzed in a prior post, dispensed with the dividend yield and assumed the required return would be roughly equivalent to the growth rate of nominal GDP. This was clearly a short cut and could be considered sloppy.1 For this post we fix that so that the risk premium is calculated via a simplified DCF.

There are also data compilation issues: the frequencies don’t all align. S&P data are daily, GDP data are quarterly, and market risk premium data are estimated annually or monthly (but with a much shorter time frame). Hence, we decided to go with annual data since that would provide us with the longest overlapping series, starting in 1960. Such frequency matches the shortest time horizon for most longer term oriented professional and individual investors. Many, however, use shorter time spans.

Finally, let’s summarize how each method is constructed:

    Naive: This is our benchmark. It essentially takes last year’s return as the predictor for next year’s.

    Historical: This is the cumulative return for the data series. Hence, as we roll forward in time any single year’s influence on the prediction decreases at a decelerating rate.

    DCF: This is the expected return calculated using the Gordon Growth model, based on the S&P’s dividend yield, and nominal GDP growth, as a proxy for the growth rate. GDP growth is calculated using the twelve months ending in the third quarter. Recall, final GDP data are delayed by a quarter, so anyone conducting the analysis in real time would only have third quarter data available at year-end.

    Risk premium: This is the market risk premium plus risk-free rate, as published by Prof. Kenneth R. French on his website: http://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html


Gordon Growth Model: https://en.wikipedia.org/wiki/Dividend_discount_model

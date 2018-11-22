## Introduction
This project revolves around determining the efficacy of Wall Street analysts’ upgrades/downgrades in relation to future stock returns, net of the S&P 500 (“market”) return .

Wall Street is a highly complex “game” between a myraid of “players” -- from institutional bankers to retail investors, all seeking to claim the best possible returns on the finite “resource” that is the stock market. It is well-known that dynamics of these market participants, especially for the retail investors, exhibit herd-like behaviors; irrational exuberance and the psychology of reward, coupled with varying levels of risk aversion create a dichotomy between “leaders” and “followers” in the market -- ‘buy, buy, buy! Its going up!....oh it’s going down sell, sell, sell!’ -- such that it is those with most efficient and strongest access to information that “lead” the herd-pack into a desired direction, and then reverse action as euphoria climaxes. In this picture, institutions are the leaders, and often times retail investors (layperson investors/traders/etc.) follow their recommendations. 

This game of bellwethers has produced numerous adages in financial marketplaces: from Baron Rothschild’s proclamation in the 18th century “buy when there is blood on the streets” to Warren Buffett’s ““Be fearful when others are greedy and greedy when others are fearful” (https://www.investopedia.com/articles/investing/012116/warren-buffett-be-fearful-when-others-are-greedy.asp). These quotes typify an unwritten rule on Wall Street: do the opposite of what analysts say, and often times one will be come out correct. Indeed, this is a cynical hypothesis, stemming from the assumption that institutions like Goldman Sachs take advantage of retail investor irrational exuberance/herd-like psychology by “unloading” and/or buying precisely at their most euphoric/dire points. 

*My own personal experiences working on Wall Street form this opinion and project hypothesis* 

## Plan

The plan is to analyze effects of analyst upgrades/downgrades on future stock performance, namely we seek to find the distribution of returns, excess market, of stocks who have been upgraded/downgraded 1 month, 3 month, 6 month, 1 year, and to-present ago. A resultant normal distribution would imply these analyst actions have no meaning; a positive-skewed distribtion would imply following analysts’ advice is a sound strategy; a negative-skewed distribution on certain timeframes would provide evidence for the hypothesis that analysts’ actions are at the expense of the retail investor. 

## Data Sources
Now, a lot of financial data is not free -- either the number of securities is limited or the historical purview is cut-off for “free” / open data. For the purposes of reproducibility, we only use “free” data sources, with the acknowledgement that the sample size and window of upgrades/downgrades may be slightly limited. 

### Stock Pricing Data 
Stock pricing data will come from Quandl’s EOD Stock Price Data ( https://www.quandl.com/data/EOD-End-of-Day-US-Stock-Prices/documentation/product-overview). 
The data source used is technically a premium subscription, but a free sample is made available. The securities in this sample are those in the Dow 30 / Dow Jones Industrial Average. Because these basket of names are well-known and highly traded, these stocks can duly serve as the basis for all analysis henceforth.

The license and terms of use for this dataset are from the “pricing page” ( https://www.quandl.com/data/EOD-End-of-Day-US-Stock-Prices/license/385) . We show key excerpts regarding usage, attribution and redistribution below: 

- Usage: “Simplified: You may use the data for academic purposes only.”
- Redistribtution: “Your use of the Services and the Services Data is personal to you, and you may not transfer or make available access to either the Services or the Service Data to others. The Services Data may only be used on electronic devices owned or operated by you as an individual. You may not publish, disseminate, re-distribute or share the Services Data, or any part thereof, or any derivative data that allows reverse engineering of part or all of the Services Data, with anyone else. You may not offer the Service Data, or any part thereof, for sale, rent, license or commercial redistribution. Any sharing or distribution by you of your access privileges or of the Services Data may result in cancellation of your use of the Services and the Services Data without refund. Simplified: Don’t share the data or your access to it. If you do, we may cancel your access.”
- Attribution: “If any part of the Services Data including derivations is displayed to the public in any form or otherwise published, it must be accompanied by an attribution in easily readable form within the same display, whether online or in print. If in print, the attribution must read “Data from QuoteMedia via Quandl”. If online, the attribution must read “Data from QuoteMedia via Quandl” and the attribution text must be hyperlinked to https://www.quandl.com. Simplified: If you present the data publicly in some way, attribute it properly.”
- Displaying Data: You may post charts or other types of data displays containing limited amounts of the Services Data on a personal blog, website, social media account, research publication, newsletter, journal or email, with proper attribution.

This license is therefore quite strict in terms of re-use and sharing. Although this license is applicable to the paid/premium data feed subscription, for safety we assume it as applicable for this project. Proper attribution will be used in all pertinent situations in the project. Furthermore, due to the redistribution and displaying clauses, only graphs of statistical analysis, et al will be shown in the final presentation and report. None of the underlying stock data will be made publically available. 

As a result, the Python code associated with this project will clearly demonsrate steps taken for interfacing with the free version of this API (just as used in this report), but the data itself will not be displayed i.e. in a Jupyter Notebook in the final repository. It is up to the reader/user to recreate the data using his/her/their own API keys, which can be freely created upon making a Quandl account. 


Upgrade/Downgrades Data 
Historical analyst action data will come from FinViz, a free stock data/screener service. For example, the following analyst upgrades/downgrades for Apple, Inc. (NYSE:AAPL) will be retrieved from https://finviz.com/quote.ashx?t=aapl. An excerpt is shown here: 

Nov-20-18
Reiterated
Goldman
Neutral
$209 → $182

Nov-15-18
Reiterated
Morgan Stanley
Overweight
$253


Such data will be accessed through an HTML parser such as BeautifulSoup4 in Python (https://pypi.org/project/beautifulsoup4/). . Of note is that the time frame for historical analyst ratings vary by security; more followed or active securities will have more frequent analyst actions. However, this will not cause any issues, as we demonstrate in the statistical analysis plan below: 

## Statistical Analysis Plan
```
For every ticker s in the Dow 30 do: 
    Generate the dates DP where the analyst upgrades were “UPGRADE” or “INITIATED”
    Generate the dates DN where the analyst upgrades were “DOWNGRADE”
    For all days x in DP do: 
      Compute the return on s on the intervals [x+30, x+60, x+90, x+180, x+360, x-TO-PRESENT] MINUS the corresponding return on the       S&P 500 (NYSE: SPY) on the exact same time interval. Generate a dataset of these returns
	Likewise do for all x in DN
Visualize and analyze skew of resultant return distributions on post-upgrade and post-downgrade actions
```
## Potential Questions
- (From the original hypothesis): Does following analyst actions/recommendations lead to opposite results for the retail investor? 
- Do certain firms (i.e. Goldman Sachs, Stifel) yield actions of less efficacy? More efficacy? 
- What stock(s) most closely follow the actions of its analysts? Don’t follow? 
- On what time intervals do the above questions/hypothesis hold strongest? Weakest? 

## Human Centered Design Considerations
As stated above, since data itself cannot be shown, we ensure that necessary documentation is provided to fully reproduce the project using one’s own (different) API access key. 

This project is not a question in ethics or bias in data. It is a project involving statistical analysis and reprodibility of anlaysis of “formal” data, that is data that is generated from purely objectivity. I.e. there is no question that AAPL closed at XXX.XX price on some date, nor no question that Goldman reiterated AAPL’s price target on 11/20/18. 

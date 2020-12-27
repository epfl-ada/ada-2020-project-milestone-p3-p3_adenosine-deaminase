# OK Google, google the NASDAQ

## Abstract

COVID-19, the most significant "black swan incident" in 2020, seemed to add huge uncertainties to the stock market unprecedently. Here we propose to study whether we can predict the seemingly strongly COVID-related NASDAQ composite index, using several measurements of the Google Trends data. We will first use the baseline AR-1 model proposed in the paper to forecast the **closing prices** of the NASDAQ index. Then we will utilizing multiple Google Trends data to evaluate if the prediction could be improved. If so, we will further explore the sensitivity of the NASDAQ index to these predictors. This will help to understand to what extent the COVID-related news is influencing the stock market.

## Research questions

People are extremely interested in talking about the trends of stocks because of their fascinating uncertainty. As the project provides us with the opportunity to dissect the contribution of the special event, we will mainly focus on the Google Trends data in all fields to see what are actually behind NASDAQ index during this special year.

- Are these predictors enough to improve the model? 
- Which are the major factors that stir NASDAQ index during this special time? 
- Which trends are the best predictors for NASDAQ index? 

## Proposed dataset

1. [NASDAQ Compostite](https://www.marketwatch.com/investing/index/comp/charts?mod=mw_quote_tab). This dataset record the historical data of NASDAQ composite index. We will only focus on the "close" data.
3. [Google Trends data on concrete keywords](https://trends.google.com/trends/explore?q=COVID&geo=US). This dataset indicates the normalized number of worldwide queries for the give keywords "COVID". With more concrete topics, we can take our analysis one step further.
3. [Google Trends data of all categories](https://github.com/pat310/google-trends-api/wiki/Google-Trends-Categories). Google Trends divides all search queries into hundreds of categories in 3 correlated levels. We collected data from all the categories using the wonderful [pytrends](https://pypi.org/project/pytrends/) API.

## Methods

**Data collection and wrangling** 

Datasets that we need have been delineated in the previous section.

**Building the model**

We will first conduct in-sample linear regression using the AR-1 model and the same model adding Google Trends features respectively. The initial features are proposed as follows: 

- The closing value of NASDAQ composite index.
- Google Trends data on one Google Trends topic/category.

Like the baseline methods in the original paper, we will conduct a rolling-window prediction to fit out-sample regression and evaluate the MAE and improvement compared to baseline model. 

**Data analysis**

We will try to find the best predictors (Google Trends categories) that have influenced NASDAQ index a lot and dissect the underlying reason to figure out the social events that financial world is most concerned about.

## Proposed timeline

- **1 Dec**	 
	- Download and wrangle NASDAQ dataset. 
	- Crawl the Google Trends data.
	- Build the first naive version of the AR-1 model and finish basic analysis.
- **12 Dec**	
	- Try different features on keyword topics and analyze the outcomes that have showed robust correlations with NASDAQ index.
	- Prepare the plots in data story.
- **18 Dec**	
	- Conduct further analysis on all the categories of Google Trends. 
	- Explore the contributions in the perspective of different levels of Google Trends categories. Develop a simple theory that may help us find the social sector that may improve the prediction for NASDAQ index. Conclude the most remarkable social fields that financial people care about.
	- Finish the data story and start to make the video.
- **23 Dec**	
	- Finish video. 

 

## Contributions

+ Collecting NASDAQ index data: all of us
+ Crawling Google Trends data in 900+ categories: all of us
+ Data exploration and wrangling: all of us
+ Data analysis on concrete topics: all of us
+ Data analysis on categories: all of us
+ Data visualization: all of us
+ Data story: all of us

The team collaborate very well together and will work together for the video.
# Predicting NASDAQ indexes during the covid-19 pandemic

## Abstract

Covid-19, the most significant "black swan incident" in 2020, seemed to add huge uncertainties to the stock market unprecedently. Here we propose to study whether we can predict the seemingly strongly covid-related NASDAQ indexes: Healthcare and Biotechnology, using several measurements of the covid situation. We will first use the baseline AR-1 model proposed in the paper to forecast the **closing values** of the two NASDAQ indexes. Then we will analysis another three predictors including the number of newly-confirmed covid cases, the Google Trends on the topic "Vaccine", and the government response index in the model to evaluate if the prediction could be improved. If so, we will further explore the sensitivity of the NASDAQ indexes to these predictors. If not, we may have to adopt other models that are more suitable for this application. This will help to understand to what extent the covid-related news is influencing the stock market.

## Research questions

People are extremely interested in talking about the trends of stocks because of their fascinating uncertainty. As the project provides us with the opportunity to dissect the contribution of the special event, we will mainly focus on the social factors that have nothing direct to do with the NASDAQ indexes.

+ Are these three predictors enough to improve the model? How can we extract more robust features?
+ Which are the major factors that stir NASDAQ indexes during this special time? 
+ Is stock market affected by government policies significantly? 
+ Will the surge in vaccines contributes to NASDAQ indexes in the long run? 

## Proposed dataset

1. [NASDAQ Healthcare](https://finance.yahoo.com/quote/^IXHC/history?p=^IXHC) and [NASDAQ Biotechnolog](https://finance.yahoo.com/quote/^NBI/history?p=^NBI). These datasets record the historical data of NASDAQ indexes in these two covid-related sections. We will only focus on the "close" data.
2. [Covid-19 cases worldwide](https://data.europa.eu/euodp/en/data/dataset/covid-19-coronavirus-data/resource/260bbbde-2316-40eb-aec3-7cd7bfc2f590). This dataset records the newly confirmed covid-19 cases in each country. We will calculate the worldwide data based on this dataset. 
3. [Google Trends on the topic "Vaccine"](https://trends.google.com/trends/explore?q=%2Fm%2F07__7&geo=US). This dataset indicates the normalized number of worldwide queries under the topic "Vaccine" as well as the related categories.
4. [Government response index](#data). This dataset developed by the University of Oxford includes 4 indices to reflect different aspects of the level of government actions in over 180 countries. We will only use the overall government response index of the US.

**Note that these datasets are all recorded on daily basis.**

## Methods

**Data collection and wrangling** 

Datasets that we need have been delineated in the previous section.

**Building the model**

We will first conduct in-sample linear regression using AR-1 model and the same model adding three predictors respectively. The initial features are proposed as follows: 

+ Closing value of NASDAQ index (Healthcare/Biotechnology) on day t.
+ Newly confirmed covid-19 cases worldwide on day t.
+ Worldwide Google Trends data on topic "Vaccine" on day t.
+ Overall government response index of the US on day t.

Like the baseline methods in original paper, we will conduct a rolling-window prediction to fit out-sample regression and evaluate the MAE especially during the days when much news for vaccine appears. 

If "Vaccine" trends data alone is not significant in improving AR-1 model, we will apply a Bayesian method called "spike and slab" regression to obtain new categories which have high posterior probability.

To further improve the performance of our model, we will consider non-linear features.

**Data analysis**

We will dive into various aspects of the COVID that may contribute to the NASDAQ index. Details are in the "Research questions"   section.

## Proposed timeline

+ **1 Dec**	  
  + Download and wrangle datasets. 
  + Build the first naive version of the AR-1 model and finish basic analysis.

+ **12 Dec**	
  + Extract different features, try more complex models. 
  + Prepare data story.

+ **18 Dec**	
  + Conduct further analysis.
  + Finish data story and start to make video.

+ **23 Dec**	
  + FInishu video. 

 
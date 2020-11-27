# Predicting NASDAQ indexes during the covid-19 pandemic

## Abstract

Covid-19, the most significant 'black swan incident' in 2020, seemed to unprecedently added huge uncertainties to the stock market. Here we propose to study whether we can predict the seemingly strongly covid-related NASDAQ indexes: Healthcare and Biotechnology, using several measurements of the covid situation. We will first use the baseline AR-1 model proposed in the paper to predict the **closing values** of the two NASDAQ indexes. Then we will add three predictors including the number of newly-confirmed covid cases, the Google Trends on the topic 'Vaccine', and the government response index in the model and evaluate if the prediction could be improved. If so, we will further evaluate the sensitivity of the NASDAQ indexes to these predictors. If not, we may have to look for other models that are more suitable for this application. This will help to understand to what extent the covid-related news is influencing the stock market.

## Research questions

1. Can these three predictors improve the model?
2. To what extent is the predictors influencing the NASDAQ indexes?

## Proposed dataset

1. [NASDAQ Healthcare](https://finance.yahoo.com/quote/^IXHC/history?p=^IXHC) and [NASDAQ Biotechnology](https://finance.yahoo.com/quote/^NBI/history?p=^NBI): these datasets records the historical data of NASDAQ indexes in these two covid-related sections. We will only use the 'close' data.
2. [Covid-19 cases worldwide](https://data.europa.eu/euodp/en/data/dataset/covid-19-coronavirus-data/resource/260bbbde-2316-40eb-aec3-7cd7bfc2f590): this dataset records the newly confirmed covid-19 cases in each country. We will calculate the worldwide data based on this dataset.
3. [Google Trends on the topic 'Vaccine’](https://trends.google.com/trends/explore?q=%2Fm%2F07__7&geo=US): this dataset indicates the normalized number of worldwide queries under the topic 'Vaccine’.
4. [Government response index](#data): this dataset developed by the University of Oxford includes 4 indices to reflect different aspects of the level of government actions in over 180 countries. We will only use the overall government response index of the US.

**Note that these datasets are all recorded on daily basis.**

## Methods

1. We will first conduct in-sample linear regression using the baseline AR-1 model  and the same model adding three predictors respectively. The AR-1 Model is expressed as: 

![](http://latex.codecogs.com/svg.latex?\\y_t ~ y_{t-1} + y_{t-7} + cases_{t-1} + trends_{t-1} + response_{t-1})

​		![](http://latex.codecogs.com/svg.latex?\\y_t): closing value of NASDAQ index (Healthcare/Biotechnology) on day ![](http://latex.codecogs.com/svg.latex?\\t).

​		![](http://latex.codecogs.com/svg.latex?\\case_t): newly confirmed covid-19 cases worldwide on day ![](http://latex.codecogs.com/svg.latex?\\t).

​		![](http://latex.codecogs.com/svg.latex?\\trends_t): worldwide Google Trends data on topic 'Vaccine' on day ![](http://latex.codecogs.com/svg.latex?\\t).

​		![](http://latex.codecogs.com/svg.latex?\\response_t): overall government response index of the US on day ![](http://latex.codecogs.com/svg.latex?\\t).

2. We will conduct a rolling-window prediction to fit out-sample regression based on the AR-1 models and evaluate the MAE especially during the days when many news for vaccine appear. 

3. If 'Vaccine' trends data alone is not significant in improving AR-1 model, we will apply a Bayesian method called 'spike and slab' regression to obtain new categories which have high posterior probability.

4. To further improve the performance of our model, we will consider non-linear features to fit the regression.

## Proposed timeline/organization within the team

1 Dec	  Data wrangling

12 Dec	Regression & model modification

19 Dec	Writing data story

25 Dec	Making video

## Question for TAs

 
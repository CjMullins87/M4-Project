
# Iterative ARIMA Modeling:  Time Series Forecasting and Meta Analysis



### Overview

In this project we will be looking at conducting routine time-series analysis on a dataset from Zillow consisting of average home values at various zip codes from 1996 into 2018. We will use our knowledge of time-series analysis to examine periodicity in our time series. I build out several helper functions to handle transforming the dataframe into timeseries and iteratively model and forecast all 14,700 counties before conducting a meta-analysis of the results to conclude which five counties offer the best return after five years.

### Contents

1. [EDA](EDA.ipynb)
2. [Modeling and Meta Analysis](/Modeling%20and%20Meta%20Analysis.ipynb)

### Supplementary Materials

1. [Functions and Model Testing](Functions%20and%20Model%20Testing.ipynb)

### Results

A meta-analysis of forecasts found that the pinpoint 5yr forecast ROI, and ROI based on lower and upper bounds of forecast confidence, were normally distributed. As such, we initially selected the top 25% of performers in each category to satisfy the requirements of "best," assuming there would be little overlap between best and worse case ROI. There appeared to be significant overlap of the subgroups, allowing us to select stricter criteria.

At a performance threshhold of the top 1% of performers the set of candidate zip codes became much smaller. This subgroup appeared to have not only much greater average property values across time ($864K vs $207K for the total population), but in more recent history their values have increased much more than average (+$21K/yr from 2014 to 2018, vs +$17K/yr), and during the recession their homes both lost less value as a percent (17% vs 33%) and recovered their value faster (5yrs vs 9yrs) than average.

As this subset seems to have resilient and reliable property returns, it was selected for a final iterative ARIMA walk toward the five year target. ROI was evaluated by subtracting the final prediction value from the initial prediction value, and then the top five were selected.

![.](/2.PNG)

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Predicting Winners of NBA Games

## Project Authors
Jerel Novick

## Repo Contents

* Code
* Data

## Table of Contents

[1. Problem Statement](#1.-Problem-Statement)<br>
[2. Executive Summary](#2.-Tools-&-Methodology)<br>
[3. Data Dictionary](#3.-Data-Dictionary)<br>
[4. Key Takeways](#4.-Key-Takeaways)<br>
[5. Next Steps](#5.-Next-Steps)<br>

## 1. Problem Statement

The purpose of this analysis is to attempt to predict the winners of NBA games using box score statistics from a game.




[New Light Technologies](https://newlighttechnologies.com/) tasked us with estimating the affluence of a neighborhood based on the Yelp designated one to four dollar sign scale for businesses and services in a given city. While traditional methods typically estimate wealth of a locality based on demographic characteristics (e.g. income or unemployment rate), the novelty of this approach is in its use of big data related to commercial activity and cost of product and services as an indicator for affluency.

Null Hypothesis: Yelp pricepoints do not predict affluence of an area.


## 2. Executive Summary

The data from this analysis was obtain from an existing Kaggle dataset (https://www.kaggle.com/pablote/nba-enhanced-stats). The dataset covers six seasons, 2012 to 2017.  There are 30 teams in the league that play an 82 game season for a total of 7,380 games over the six seasons.

The basic framework used was a four factor model.  The overall elements of the model are shooting, turnovers, rebounding and free throws. Several variables make up each of these elements. A logistic regression was conducted on both the data for individual games and a five game moving average.

The following packages were imported to conduct this analysis.




Data was gathered from Yelp for the most populous city in each of the 50 states. The data was categorically divided into restaurants, hotels, shopping, nightlife and beauty, which totaled almost 85,000 datapoints.  The datapoints were then aggreated for each of the cities based on Yelp's price ratings ($$$, $$$, $$, $) and number of stars (1 to 5). Affluency was measured by the median household income in each of the cities. This data was retrieved from City-Data.com.

Using the Yelp data, supervised and unsupervised learning models were built to predict affluency or identify patterns in the data.

The decision was made to also build an alternate model using select socio-economic metrics, which were completed level of education of a city's residents, population density, land area, property crime rate, and violent crime rate. 

The following packages were imported to conduct this analysis.

|                |            |         |         |            |          |
|----------------|------------|---------|---------|------------|----------|
| Pandas         | Matplotlib | Seaborn | Sklearn | Numpy      | Requests |
| Beautiful Soup | YelpAPI   | Regex   | Plotly  | Statsmodel | Scipy    |

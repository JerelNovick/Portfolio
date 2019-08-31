# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Predicting Winners of NBA Games

## Project Authors
Jerel Novick

## Repo Contents

* [Code](https://git.generalassemb.ly/JerelNovick/DSI-Assignments/tree/master/Capstone/code)
    * [Data Import and Cleaning](https://git.generalassemb.ly/JerelNovick/DSI-Assignments/blob/master/Capstone/code/data_cleaning.ipynb)
    * [EDA](https://git.generalassemb.ly/JerelNovick/DSI-Assignments/blob/master/Capstone/code/EDA.ipynb)
    * [Four Factor Model](https://git.generalassemb.ly/JerelNovick/DSI-Assignments/blob/master/Capstone/code/four_factor_model.ipynb)
    * [Moving Average Model](https://git.generalassemb.ly/JerelNovick/DSI-Assignments/blob/master/Capstone/code/ma_models.ipynb)
* [Data](https://git.generalassemb.ly/JerelNovick/DSI-Assignments/tree/master/Capstone/data)

## Table of Contents

[1. Problem Statement](#1.-Problem-Statement)<br>
[2. Executive Summary](#2.-Tools-&-Methodology)<br>
[3. Data Dictionary](#3.-Data-Dictionary)<br>
[4. Key Takeways](#4.-Key-Takeaways)<br>
[5. Next Steps](#5.-Next-Steps)<br>

## 1. Problem Statement

The purpose of this analysis is to attempt to predict the winners of NBA games using box score statistics from a game.  The ultimate goal is to create a profitable betting strategy.  This represents the first steps in this process.

Where sports gambling is now legal in 12 states and more considering legalization, the hope is to develop a model that can either be used to profitably predict the results of games.  Alternatively, the model could be applied to the other side of the counter.  Either to create moneylines (probabilities) for game or used in the birgining sport integrity business.


## 2. Executive Summary

The data from this analysis was obtain from an existing Kaggle dataset (https://www.kaggle.com/pablote/nba-enhanced-stats). The dataset covers six seasons, 2012 to 2017.  There are 30 teams in the league that play an 82 game season for a total of 7,380 games over the six seasons.

The basic framework used was a four factor model.  The overall elements of the model are shooting, turnovers, rebounding and free throws. Several variables make up each of these elements. A logistic regression was conducted on both the data for individual games and a five game moving average.

The following packages were imported to conduct this analysis.

|        |         |                  |            |
|--------|---------|------------------|------------|
| Pandas | Numpy   | Pandas Profiling | Matplotlib |
| Scipy  | Sklearn | Seaborn          | Warnings   |

## 3. Data Dictionary


| Feature     | Type    | Description                                                        |
|-------------|---------|--------------------------------------------------------------------|
| gmDate      | date    | Game date                                                          |
| seasonYR    | integer | Season that the game was played                                    |
| teamAbbr    | string  | Abbreviation of team                                               |
| teamLoc     | string  | Identifies whether team is home or visitor                         |
| teamRslt    | string  | Identifies whether team has won or lost                            |
| teamDayOff  | integer | Days since the teams last game                                     |
| teamTO      | integer | Team turnovers                                                     |
| teamPF      | integer | Team personal fouls                                                |
| teamFGA     | integer | Team field goal attempts                                           |
| teamFGA     | integer | Team field goals made                                              |
| teamFTA     | integer | Team free throw attempts                                           |
| teamFTM     | integer | Team free throws made                                              |
| teamORB     | integer | Team offensive rebounds                                            |
| teamDRB     | integer | Team defensive rebounds                                            |
| teamEFG%    | float   | Effective field goal percent by team                               |
| teamTREB%   | float   | Total rebound percent by team                                      |
| teamTO%     | float   | Turnover percentage by team                                        |
| teamFT%     | float   | Free throw percentage made by team                                 |
| MAteamFGA   | integer | Five period moving average of team field goal attempts             |
| MAteamFGM   | integer | Five period moving average of team field goals made                |
| MAteamTO    | integer | Five period moving average of team turnovers                       |
| MAteamORB   | integer | Five period moving average of offensive rebounds                   |
| MAteamDRB   | integer | Five period moving average of defensive rebounds                   |
| MAteamFTA   | integer | Five period moving average of team free throw attempts             |
| MAteamFTM   | integer | Five period moving average of team free throws made                |
| MAteamPF    | integer | Five period moving average of team personal fouls                  |
| MAteamEFG%  | float   | Five period moving average of effective field goal percent by team |
| MAteamTO%   | float   | Five period moving average of turnover percentage by team          |
| MAteamTREB% | float   | Five period moving average of total rebound percent by team        |
| MAteamFT%   | float   | Five period moving average of free throw percentage made by team   |

## 4. Key Takeaways

While the initial models showed showed high levels of accuracy, they were much less predictive of teams with more losses.  Employing moving averages reduced the level of accuracy.


## 5. Next Steps

The next steps are:
    * Creating and employing better metrics
    * Looking for more interactions
    * Calculating the model's winning probabilities
    * See were the model is correctly predicting "dogs" to win over favorites
    * Creating Pythagorean Expectation and Log 5 Models
    * Looking for value against moneylines
    * Expanding the model to look at NCAA games

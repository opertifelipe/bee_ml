# Bee ML - Machine Learning model for honey production prevision

This project shows a simple model able to predict the percentange growth of honey produced by a hive with seven days in advance. This model should be useful for all beekeepers that would like to improve their production.

## Data 
All data are downloaded from Kaggle from the url https://www.kaggle.com/se18m502/bee-hive-metrics. Here, I use the data of humity, temperature and weight of the years 2017-2019 of two hives (from Wurzburg and Schwartau in Germany).

## Preprocessing

*Features:* The data show the temperature and the humidity measureed each hour for the time interval 2017-2019. From them I calculate the max, the min e the mean of each quantity for seven days. These should the information about the weather. Furthermore, I add the month feature as addictional info about the season. 

*Target:* The target is gived by the percentual difference between the honey in seven days by the hive. Furthermore I added two extremes that are 100% more of production, and -100% less of production. This was added to esclude outliears that can affect the regression.

## Model


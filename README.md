# Bee ML - Machine Learning model for honey production prevision

This project shows a simple model able to predict the percentange growth of honey produced by a hive with seven days in advance. This model should be useful for all beekeepers that would like to improve their production.

Normally beekeepers divides the hives in several place to improve the production because, normally, in some place they produce more and in other less. The aim of this project is to know in advance the best place to put hives. Indeed the beekeeper each week should place the hives in different places to improve the production.

## Data 
All data are downloaded from Kaggle from the url https://www.kaggle.com/se18m502/bee-hive-metrics. Here, I use the data of humity, temperature and weight of the years 2017-2019 of two hives (from Wurzburg and Schwartau in Germany).

## Preprocessing

*Features:* The data show the temperature and the humidity measureed each hour for the time interval 2017-2019. From them I calculate the max, the min e the mean of each quantity for seven days. These should the information about the weather. Furthermore, I add the month feature as addictional info about the season. 

*Target:* The target is gived by the percentual difference between the honey in seven days by the hive. Furthermore I added two extremes that are 100% more of production, and -100% less of production. This was added to esclude outliears that can affect the regression.

## Model
I trained the data using four method: Gradient Boosting Regression, Linear Regression, Polynomial Regression, and Random Forest. After that I evaluated them calculating the RMSE. The result shows that the Random Forest Regression is the best tecnique in this case.

## Usage

The aim of the project is to show the possility to improve the production of honey using a machine learning model. Dowloading the weather forecast for the next week and given the month, each week the beekeeper will know the best place to hold the hives.

## Next steps
Here a list several important next step:
- Increase the amount of data. I used the data coming from only two hives. Therefore, it is really important to improve the amount of data from more hives.
- Define different targets and create several models to define which is the place to locate the hives for the next week.
- More features. Here I used temperature and humidity. Probably more features should improve the result. 
 

# Bee ML - Machine Learning model for honey production prevision

This project shows a simple model able to predict the percentage growth of honey produced by a hive seven days in advance. This model should be useful for all beekeepers that would like to improve their production.

Normally, beekeepers divide the hives in several places to improve the production because in some places they produce more and in other less. The aim of this project is to know in advance the best place to put the hives. Indeed the beekeepers each week should place the hives in different places to improve the production. 

## Data 
All data are downloaded from Kaggle from the url https://www.kaggle.com/se18m502/bee-hive-metrics. Here, I use the data of humidity, temperature, and weight of the years 2017-2019 of two hives (from Wurzburg and Schwartau in Germany).

## Preprocessing

*Features:* The data show the temperature and the humidity measured each hour for the time interval 2017-2019. From them I calculate the max, the min e the mean of each quantity for seven days. These are the information about the weather. Furthermore, I add the month feature as additional info about the season. Indeed, this last feature is a proxy for the seasonal flowering. During the train phase we have the real weather data from the control units located in each hive. During the scoring phase, the beekeeper should use weather forecast to create the features and provide the result. 

*Target:* The target is given by the percentage growth of the honey produced in a week by the hive. For example, if on Monday the hive weighs $w_m Kg$ and on the next Sunday the hive weighs $w_s Kg$, therefore the target $\Delta_w = 100*\frac{w_s-w_m}{w_m}$. Furthermore I added two constraints: $-100 \leq \Delta_w \leq 100$. Values outside these constraints are reduced to respectively $-100$ and $100$.

## Model
I trained the data using four regression model: Gradient Boosting Regression, Linear Regression, Polynomial Regression, and Random Forest. After that I evaluated them calculating the RMSE. The result shows that the Random Forest Regression is the most performing technique with $RMSE=18.2$. The optimal parameters are calculated using the grid search and using cross validation with three folders. 

## Conclusion

The aim of the project is to show the possibility to improve the production of honey using a machine learning model. Downloading the weather forecast for the next week and given the month, each week the beekeeper will know the best place to hold the hives with an error of 18%. The error is large and it is probably due to the small dataset that I used indeed I only have data about two hives. Furthermore, I used few estimators in the random forest to reduce the processing time.    

## Next steps
Here a list of important next steps:
- Increase the amount of data. Indeed, the error is large and it is probably due to the small dataset that I used (I only have data about two hives). It is really important to improve the amount of data from more hives.
- Increase the number of estimators in the random forest regression. I used a few number of estimators and a low variety of parameters in the grid search to reduce the processing time. However for a more assertive model the search should be wider. 
- Define different targets and create several models to define which is the place to locate the hives for the next week. In this project I defined only the target $\Delta_w$. 
- More features. Here I used temperature and humidity. Probably more features should improve the result. 
 
## Contents

The project contains three files:
- requirements.txt: software requirements.
- README.md: readme file about the project.
- bee.ipynb: Jupyter Notebook with model and analysis 


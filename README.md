# Kaggle-Housing-Prices

This code creates a Linear Regression model that predicts house prices for the Kaggle Housing prices competition (linked below): 
<br>(https://www.kaggle.com/c/house-prices-advanced-regression-techniques)
Inspiration for initial data cleaning:
<br>https://www.dataquest.io/blog/kaggle-getting-started/
<br><br>This was my first chance to explore Machine Learning techniques that included data cleaning, feature engineering, and data visualization prior to building my model. Over 70 features are included in the dataset, so a big component of building a successful model is finding the features that are significant in building one. To begin with, I referenced some other submitted codes and once I got a feel for how they did their feature engineering, I worked on doing some of my own changes on top of that. I began by splitting the data into Numerical and Categorical features. Using the correlation of the numerical features, I limited the list of features I used to those that were the most highly correlated to the Sale Price of a house (positively or negatively). From there, I explored each of the numerical features I planned on using in the model, and removed outliers that would harm its generalizability. I started with the most highly correlated features because I was more liberal with removing outliers from the most important features. After that, I explored some of the categorical features and converted some into dummy variables that could be interpreted by the model more easily (e.g. Abnormal sale condition resulting in a higher sale price, while the other conditions were relatively equal).
<br><br>After the data cleaning and feature engineering, I split my training data into a train and test set, and worked to tune my Linear Regression model based on the Mean Squared Error. In addition to this tuning, I wanted the model to be more generalizable so it would perform better on the actual test data. I used statsmodels to create my LR models because of the statistical summary it provides. I began by creating a Linear Regression model with each predictor, then with all predictors at once. I wanted to see if any p-values pointed towards a predictor being insignificant (with alpha = .05). After that, I incorporated interaction terms into my model along with quadratic terms as well. I removed each insignificant predictor based on the hierarchical principle (keeping each base variable if a more complicated term was found to be significant), and used my final model to predict on the entirety of the training set, along with the test set.
<br><br>In future iterations of this code, I want to spend more time exploring the categorical features. There could be other variables that are significant in determining Sale Price that I have not considered yet. Additionally, I wanted to expand to using more Machine Learning Algorithms. After looking through the leaderboard for this competition, I know that Linear Regression does not perform optimally on the test set of data. However, I do think there is a lot of interpretability to be gained from using a LR model.

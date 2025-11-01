In this project, I train an OLS regression and a support vector regressor to predict the next day's close of financial company. Sometimes, excutives and analysts are curious about how their 
company will perform in the future, given their current performance. However, they may not have the ability to build a model that's been trained on their company data. How can executives work 
around this dilema and still predict their companies future?

One idea is the company uses an already trained model from an organization in the same or similar field. Hypothetically, if a well trained model has picked up on the stock performance patterns 
of other companies, maybe those patterns are generalizable and can be used to make robust predictions for another company. The models designed below perform the following: predict the stock 
patterns of companies D and E, after being trained on stock data from companies A, B, and C. 

The former model was selected because it's designed for linear data. The latter model was selected because its hyperparameters (the selected kernel) can be modified to best fit linear data. 
Although no tests have been performed to asses the complexity of the relationship between our X and Y, it's apparent that many of our features are similar, which could result in colinearity. 
This means our features can be written as linear combinations of each other, resulting in a linear relationship. Thus, we select models that fit well to data with a linear relationship. 

Our X_train is the 'Open', 'High', 'Low', 'Volume' data from JP Morgan, Paypal, Metlife, and AIG. Our X_test comprises of these same columns but for Goldman sachs. y_train is 'Close' data for 
JP Morgan, Paypal, Metlife, and AIG. y_test is this same column, but for Goldman Sachs. 

It is important to note that each observation in the X predictors are "shifted"; the goal in to use "today's" stock data to make market predictions for "tomorrow". For example: take an 
observation from November, 4 2024. While our X_train data describes November 4, 2024's stock market, the y_train describes November 5, 2024's close data. This way, our model is learning how to 
predict tomorrows trends from today's data. This is the same case for the test set. 

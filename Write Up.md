# The Roger-Ebert Bot

Crystal Huang

## Abstract

The goal of this project is to use linear regression model to predict the renowned late movie critic Roger Ebert's film rating if he were alive today. My primary and secondary datasets were obtained through webscraping process. Using numerical and categorical features, along with some feature engineering, I built some linear regression models. After multiple trials of 5-folds cross-validation test, modifying datasets, and more feature engineering, my final linear regression model with lasso regularization has R-squared value of 0.366 and mean absolute error of 0.55, which in layman's term, the prediction is off by 0.5 star. 

## Design

As a movie lover, I have always enjoyed watching and discussing movies with friends. When it comes to professional movie critiquing, the late Mr. Roger Ebert had reviewed the most and is the best known movie critics of all time. For this linear regression project, I want to analyze what affect's Roger Ebert's rating and see if we can predict Roger Ebert's movie rating if he were alive today? 

## Data

The primary dataset was web-scraped from the film critic's website rogerebert.com with Python's BeautifulSoup and Selenium libraries. Once the data was collected and cleaned, I realized that there wasn't enough features to create a robust model. I wanted other features such as users ratings and box office information. From Kaggle, I found a dataset containing other large movie rating sites - MovieLens and IMDb information for the movies. With the IMDb ID from this dataset, I was able to do a second data scraping from IMDb.com for the additional features. I decdied not to scrap Rotton Tomato's rating and Metacritics Scores since those rating takes in the critics' rating for average score. My original dataset contains 7847 datapoint and 6 features. After data merging and cleaning, I have 2191 datapoint and 11 features.

## Algorithms

*EDA*

Each datapoint is an individual movie. The target variable is Ebert rating (on a sale from 0.0 to 4.0). Of the 11 features, there are 3 categorical features - Genre, sub-genre and MPAA rating (which are convert into dummy variables in feature engineering process). The numerical features include year(movie released), runtime(in minutes), movieLens rating (on a scale from 0.0 to 5.0), IMDb rating (on a scale from 0.0 to 10.0), budget, domestic gross, opening week gross, and worldwide gross. 

Looking at Ebert's rating distribution, I see that he gave almost half of the movies a 3 to 3.5 rating and he also does not give too many terrible movie ratings like 0 to 0.5 stars, which might affect the model prediction in lower rating. 

Using pairplot and heat map, I found movieLens rating and IMDb rating have higher coefficient with the target variable. But other numerical features do not seem to have apparant linear relationship with the target variable, which indicates some feature engineering might be needed.

*Feature Engineering*

1. Mapping genre and subgenre columns to less categories (eliminate outliers)
2. Converting categorical features to dummy variables
3. Create new features with some feature interaction (i.e. Opening week gross proportion calculated by opening week gross divided by cumulative worldwide gross)
4. Power transform some numerical features to help with avoiding the outliers

*Models*

My baseline model has a R-squared of 0.382, using the 9 features with p-values of less than 0.05. I built another 3 models - polynomial, Ridge and Lasso and then I use 5-folds cross-validation test to evaluate which model performs the best. However, the results shows no major difference between the models. R-squared valeus are close and low between models and between train and validation sets. This suggests that models may be underfitting. To improve my model, I increase complexity by adding more features and more feature engineering.

Besides the previous 4 models, I also tried using Ridge and Lasso regularizations on polynomial. Since polynomial has higher training score than validation score, it indicates the polynomial model is overfitting. So I used Ridge and Lasso and tuned the regularization strength to hopingly find the sweet spot in the bias-variance trade-off graph.

*Model Evaluation and Selection*

After iterative process of model refinement, tuning, and selection on validation test, my final linear regression model with lasso regularization has R-squared value of 0.396 and mean absolute error of 0.55 which in layman's term, the prediction is off by 0.5 star. It performed slightly better than the other models. 

**Final Lasso model 5-fold CV scores:**

* R-squared value: 0.366
* RMSE: 0.691
* MAE: 0.563

**Holdout**

* R-squred value: 0.371
* RMSE: 0.707
* MAE: 0.559

## Tools

- BeautifulSoup and Selenium for web-scraping
- Pandas and numpy for data manipulation
- pickle for data storage
- Matplotlib and seaborn for plotting
- scikitlearn and statsmodel for modeling and testing

## Communication

[Presentation slides](Regression Presentation.pdf)

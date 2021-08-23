# ***Predicting Home Prices***
### By: Corina Lentz

## ***Problem Statement***

The real estate market climbed to $36.2 trillion in 2020 [*source*](https://www.forbes.com/sites/brendarichardson/2021/01/26/housing-market-gains-more-value-in-2020-than-in-any-year-since-2005/). In 2021 the demand for homes has only increased [*source*](https://www.cnn.com/2021/06/16/homes/us-housing-market-offers/index.html). With this booming real estate market, predicting how much a home will sell for with a reasonable level of accuracy is more important than ever. That is where Lentz Data Analysis comes in. We will use data collected from Ames, Iowa house sales to build a multiple linear regression model that can predict the sale price of homes within a certain amount. We believe the most accurate model will have the overall quality of the home, the home type, and the number of bedrooms/bathrooms, along with measurements of the size and quality of any basement or garage features of the home. 

## ***Data Dictionary***

The data dictionary that I'm referencing for this dataset is found here: https://www.kaggle.com/c/dsir-524-project-2-regression-challenge/data .

## ***Data Cleaning & Processing***

The dataset that was provided for this project is the Ames Iowa Housing dataset. It is made up of 81 columns and 2051 rows detailing numerous features of homes that were sold between 2006-2010 in Ames, Iowa. The dataset had many missing values that needed to be addressed. After reviewing the data dictionary we discovered that the majority of the missing values indicate the home doesn't have that particular feature or amenity and we updated these values accordingly. There were four columns that had less than 20% of non-null values that we ultimately decided to drop from the dataset. 

## ***Modeling***

In choosing the variables for our model, we used the relationships we discovered during EDA (particularly through the heatmap) to select features that would have the most impact; while also focusing on features that aligned with our initial hypothesis. We selected features that:

- Measure the overall quality of the home

- Indicate the home type

- Measure the number of bathrooms/bedrooms

- Measure the overall size of the home

- Measure any additional home features (garage, basement, etc)

- Measure the quality of any additional home features

In the end we had 18 numerical features and 9 categorical features (that we processed through one-hot encoding), for a total of 68 feature columns that were used in our multiple linear regression model.

## ***Results***
After fitting our linear regression model we completed a train-test-split to see how effective our model was at predicting the home sale price. Results included in the table below. The train and test scores show that our variance is pretty low. The R-squared score indicates that 85.5% of our model's variance is explained by our features, with all else remaining constant. However the RMSE shows our sale price predictions are off by about $30k. Some of the coefficients for our features are inconsistent as well, suggesting that outliers maybe skewing the data.  

|Measurement Name|Value|
|-|-|
|Train Score|0.8492|
|Test Score|0.8734|
|R^2 Score|0.85501|
|RMSE|30172.34|

## ***Conclusion & Recommendations***
The features that we included in our model do have measurable impact on the sale price of the home, however they do not provide the most complete or accurate calculations of the sale price. Our hypothesis that the most accurate model will have the overall quality of the home, the home type, and the number of bedrooms/bathrooms, along with measurements of the size and quality of any basement or garage features of the home was not correct.

We recommend using this model to develop an even more accurate model by dropping outliers from the data, possibly removing some of the redundant features (such as ‘Total Bsmt SF’ when we have ‘Bsmt Fin SF’) and adding in other features that may offer better insight such as measurements of the masonry and decks included in the home.

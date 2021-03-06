![topimage](https://user-images.githubusercontent.com/71023894/115910844-56ba2e80-a43b-11eb-8851-3fc48e0a68bc.png)


# Machine Learning Project: Predicting Airbnb Rental Prices
Our team aimed to predict major US and European cities' rental price based on US Airbnb rental price data using supervised learning methods. The main questions of interest are:
  1. How well can our model predict American Airbnb prices? 
  1. Will the model trained on US data generalize to European cities? 
  2. What are the important features in predicting Airbnb prices? 

This model could be helpful to home and apartment owners trying to determine a good price for their listing, by offering an estimate of what similar units in the area are priced at, it helps to establish a baseline. On the renters end, having a price prediction can help them determine whether or not the apartment they are considering is a good deal or not. 

We see the benefits of this project reaching beyond just Airbnb, the same principles used in this project can be applied to a wide variety of real estate tech companies. Our model will likely be fairly easy to translate to companies like Zillow, traditional real estate agencies, and the countless real estate tech companies popping up working to improve the refinance of the mortgage industry. In a more general sense building an effective revenue boosting Machine Learning algorithm is applicable to virtually every company in the world. This will be a good way to integrate the machine learning topics from class to a real dataset.


## I. Data Sources
For this study, four datasets were acquired, cleaned, and merged together to create comprehensive train and test datasets. 

Kaggle: Airbnb Data in Major US Cities
This dataset contained the price and characteristics of various Airbnb listings in six major US cities -- Boston, Chicago, Los Angeles, New York, San Francisco, and Washington D.C. The initial dataset contained information on over 74,000 distinct Airbnb properties and 28 features. It was ultimately split into training, validation, and test sets.

This dataset can be downloaded here: https://www.kaggle.com/rudymizrahi/airbnb-listings-in-major-us-cities-deloitte-ml

Inside Airbnb: Airbnb Data in Global Cities
Inside Airbnb contained the price of Airbnbs and over seventy characteristics of listings in major cities worldwide. To test for model generalizability abroad, we selected three prominent cities in Western Europe -- Madrid, London, and Paris.

This dataset can be downloaded here: https://www.kaggle.com/rudymizrahi/airbnb-listings-in-major-us-cities-deloitte-ml

Simple Maps: City Data
The simple maps data was merged onto the Airbnb data on city to obtain population and the longitude and latitude of the city center of a city. This was crucial to several of the features we engineered to improve model predictivity.

This dataset can be downloaded here: https://simplemaps.com/resources/free-country-cities

World Data: Cost of Living Index
As mentioned previously, housing data often requires normalization when being compared across markets. One of the ways we improved our model was by adjusting each of our international predictions based on the Cost of Living Index (CLI) associated with the relevant country. The CLI is a metric used to adjust the cost of goods and services with respect to the US.

This dataset can be downloaded here: https://www.worlddata.info/cost-of-living.php

## II. Experimental Design 
![work-flow](https://user-images.githubusercontent.com/71023894/115911394-07c0c900-a43c-11eb-9fe3-1995c22ba37d.png)


## III. Final Model
After testing out five different models (Lasso, Random Forest, XGboost, Neural Net and KNN), we concluded that the best model is Random Forest based on R-squared and Absolute Median Error. 

![result](https://user-images.githubusercontent.com/71023894/115910152-7d2b9a00-a43a-11eb-990e-0504fd89dd65.png)


## IV. Conclusion
This study developed a modeling and feature engineering approach that not only performs well at predicting Airbnb rental prices within the United States, but also abroad. Based on property characteristics and geographic features, we were able to train multiple models that generalized beyond just the city or geographic location it was trained upon. Based on predictive power, we concluded that property type, the number of bathrooms, and the distance an Airbnb is to the city center is critical in predicting the price of a listing.

The results from the Random Forest Regressor, showed that the model was able to outperform other techniques such as Lasso Regression, KNNs, XGboost, and MLP Regressors based on key metrics such as R2 and RMSE. The median prediction of this model was within about $24 of the actual Airbnb price in the US compared to $28 internationally. Considering the nightly cost of anywhere from a couple bucks to thousands of dollars, this range is acceptable.

One limitation our study did not account for is the impact Covid may have had on rental prices internationally. Since most of the training data is from 2018, while much of the international test data was acquired in 2021, there may be a difference in rental prices during those time periods. According to Forbes, 29% of American hosts listed their properties at reduced prices, especially for those considered essential workers, at the beginning of the pandemic.


## V. Getting Started

**Step 1: Clone the repo:**
```
git clone https://github.com/nikhil-bhargava/ids-705-final-project.git
```

**Step 2: Navigate your way into the repo:**
```
cd ids-705-final-project
```

**Step 3: Create virtual environment for project (pip or conda):**

**Step 4: Then install packages:**

Remember to install packages and add them to requirements.txt as you go along with the proper versions (pandas and numpy are already in there as an example).

```
pip install -r requirements.txt
```

**Step 4: Download datasets from links above in data section. Store the data in the:** `/data/raw` **folder.**

**Step 5:** Create pre-processed train and test datasets by running the following notebooks: `notebooks/00-us-preprocessing` and `notebooks/00-international-preprocessing` folders. The datasets are not included as they're larger than the github data storage limits.

**Step 6:** Run any model notebook, example for the Random Forests model run the corresponding notebook: `notebooks/01-random-forest-modeling`. This will also output the model in the `models/` folder. The models are not included as they're larger than the github data storage limits.


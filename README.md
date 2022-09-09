# Max_Daily_Energy_Predictions_Project
Max Daily Energy Prediction using Regression Analysis

Author - Udhai P Singh


![awesome](https://github.com/audi0786/Max_Daily_Energy_Predictions_Project/blob/main/Images/AEMO_price_demand_image.jpg)



## Project Overview

This project analyzes the electricity consumption of Melbourne from 01.01.2021 to 31.08.2021. It is often observed that electricity consumption has strong relation with weather, especially temperature and time of the year/season. We will analyze the relationship of electricity consumption in Melbourne based on various weather features like temperature, wind, month and so on. The goal here is to predict the electricity consumption of the city based on weather forecast. 

Our stakeholders, the electricity providers, can use this model to plan for the expected demand and hence make arrangements as participants of National Electricity Market(NEM) to lock in the expected demand at the right price.


***
## Data:

The following two datasets are used:
1. price_demand_data.csv: This excel contains price and demand for each 30 minutes period from 01.01.2021 to 31.08.2021, for Victoria, Australia. RRP column has been removed from the data. For more details, please refer to the data source: https://aemo.com.au/energy-systems/electricity/national-electricity-market-nem/data-nem/aggregated-data

2. weather_data.csv: contains various weather features like temperature, wind pressure, wind direction and so forth, for each day from 01.01.2021 to 31.08.2021. Note, that these readings are on daily interval ie. one readign per day. 

***
## Busines Problem

The retail electricity provider participates in NEM in the spot market to procure electricity to sell it to consumers. NEM participants need to manage the financial risks associated with the significant spot price volatility that occurs during trading periods. Providers hedge their risk by locking in  a firm price for electricity that will be produced or consumed at a given time in the future. These arrangements are generally in the form of derivatives, and include swaps or hedges, options and futures contracts.

In order to enter various purchasing arrangements at the right price, the demand forecast becomes critical especially the maximum demands for which the retails need to be prepared, otherwise purchasing units from the spot market at last minute to meet unexpected peak demand is exorbitantly expensive as compared to long term derivatives. 

To solve this problem for our stakeholders, we are trying to predict the daily maximum electricity demand based on weather forecast for Melbourne. 



***
## Methods

In order to predict daily maximum electricity demand, I have performed Multiple Linear Regression. 

The main steps in my analysis of this projects are:

1. Data Cleaning: to prepare the data for further analysis and model implementation

2. Exploratory Data Analysis: 

2. Feature engineering: This step involved changing data types for some of the features as well as relying on extensive visualizations for creating new features which would aid our prediction model. Some of the feature engineering was performed while carrying our different iterations of the model, as explained in the next step.

***
### Iterative approach

![awesome](https://github.com/audi0786/Max_Daily_Energy_Predictions_Project/blob/main/Images/five_iterations.jpg)


3. In order to arrive at our final model, i have used an iterative approach. Start from a basemodel with just three features, which were mostly strongly correlated with our dependant variable. We performed a linear regression and the base model performed well. 

Note: We choose a stratified cross validation method so as to ensure that in a small dataset of 243 rows we are able to get enough entries 
in each split which are representative of each class. If a simple split test is performed it can be misleading and can have high variance between different iterations of the model. Hence this appraoch in this case is more reliable. 

4. Next iteration of the model: was introdcing all the features from our dataset in the model. Here we observe that the model metrics are actually worse off than even the base model. Hence we need to make changes in our model. 

5. Log transformed and scaled model: Here we selectively performed log transformations as well as feature scaling. This model has shown improvements in both mse train and test set as well as r2 values for both train and test set at the same level. 

Note: It is important to keep in mind that whenever we talk about any model metrics; they are average of five splits. as we applied stratified KFold with n_splits = 5. 

6. Next iteration: Feature Selection using f_regression: Here we found out the best features for our model based on the f_regression score.
Even the f_regression was performed on three splits to ensure the consistency in the f_scores of the features. 
After running our linear regression model with only 10 highest f_score features, our model improved significantly. The model score increased from -0.1 to 0.05 and all r2 scores and mse scores improved. 

7. Iteration: Polynomial and interaction features: In our next iteration of the model, we choose three out of the ten features to create more polynomial and interaction features. Our model improved significantly. Its model score increased from 0.05 to 0.22. This is the best model score we have till now. We have r2_test score of 0.47 and with this score going as high as 0.75 in one of the train-test splits. 

***
***
![awesome](https://github.com/audi0786/Max_Daily_Energy_Predictions_Project/blob/main/Images/keytakeaways.jpg)



## 1. As expected, the hour of the day matters even on a eight month span. Electricity consumption is maximum at 6pm in the evening. Whereas the mean hourly electricity consumption dips to a minimum at 3 am. So this should inform at what time most generators come on and off the grid. This should inform the hourly forecast of the retail distributors. 


![awesome](https://github.com/audi0786/Max_Daily_Energy_Predictions_Project/blob/main/Images/hourly_forecast.png)



## 2. Lineplot demonstrates weekdays consume more Max energy than weekends for all months except January. This is due to abnormally huge demand on 11.01.2021 and 25.01.2021.  While the spike on 25.01.21 is explainable as it is part of the long weekend ago and maybe associate with Australia day celebrations. On the other hand, the spike on 11.04.22 seems like an abberation. Hence, our stakeholders needs to be prepared for these anamolies. 

![awesome](https://github.com/audi0786/Max_Daily_Energy_Predictions_Project/blob/main/Images/day_Vs_month_relationship.png)


### Another anamoly in data is that weekend mean-max consumption dips in February whereas for weekdays it dips in March

### The second change of trend for both weekend(0,6) and weekdays(0-4) is simultaneously in August where it breaks the increasing trend. 



## 3. For our stakeholders - July seems to be a critical period at the max consumption for both weekdays and weekends peaks together, hence the max capacity and the base load for July will increase substantially as compared to other months


![awesome](https://github.com/audi0786/Max_Daily_Energy_Predictions_Project/blob/main/Images/dayvsmonth2.png)



## 4. Our final model with scaled, polynomials and interaction features is performing well and is able to explain 0.47 of variations in unseen/test data. 


##  More Information
See the full analysis in the Jupyter Notebookat https://github.com/audi0786/Max_Daily_Energy_Predictions_Project

For additional info, please contact Udhai P Singh at singhudhai16@gmail.com


## Badges

[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)

## Repository Structure

.
├── .ipynb_checkpoints      # checkpoints
├── images                  # Images used in notebook and README.md
├── data                    # Source data
├── Daily_Energy_Demand_Prediction_via_Regression_Analysis.ipynb    
├── Notebook.pdf            # PDF copy of the notebook
├── README.md



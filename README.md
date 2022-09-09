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


3. In order to arrive at our final model, i have used an iterative approach. Start from a basemodel with just three features, which were mostly strongly correlated with our dependant variable. The base model performed well. 






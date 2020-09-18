# Predict-Future-Product-Sales
---

## Project Overview

- Objective : To predict future product sales 
- Time Series Forecasting Model
- Data cleaning and Data preprocessing has been done to optimize features
- Exploratory Data Analysis
- Facebook Prophet Time Series Forecasting Tool is used.
- Predict future weekly, monthly and yearly trends with and without holidays impact

---
## About Project

Predicitive models are developed for companies to forecast sales in future which helps them to grow in competitive and sky-rocketing markets. These models aim to forecast sales based on historical trends while taking into account promos, school holidays and state holidays.

---
## Code and Resources used

- Python version: 3.7.6
- Packages: Pandas, Numpy, Seaborn, Matplotlib and Prophet
- Resources used:

  * https://facebook.github.io/prophet/docs/quick_start.html#python-api
  * https://towardsdatascience.com/predicting-the-future-with-facebook-s-prophet-bdfe11af10ff

---
## Web Scraping

Dataset URL: https://www.kaggle.com/c/rossmann-store-sales/data

Historical sales data for 1,115 Rossmann stores. The task is to forecast the "Sales" column for the test set. Note that some stores in the dataset were temporarily closed for refurbishment.

### Data fields

Most of the fields are self-explanatory. The following are descriptions for those that aren't.

* Id - an Id that represents a (Store, Date) duple within the test set
* Store - a unique Id for each store
* Sales - the turnover for any given day (this is what you are predicting)
* Customers - the number of customers on a given day
* Open - an indicator for whether the store was open: 0 = closed, 1 = open
* StateHoliday - indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public holidays and weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None
* SchoolHoliday - indicates if the (Store, Date) was affected by the closure of public schools
* StoreType - differentiates between 4 different store models: a, b, c, d
* Assortment - describes an assortment level: a = basic, b = extra, c = extended
* CompetitionDistance - distance in meters to the nearest competitor store
* CompetitionOpenSince[Month/Year] - gives the approximate year and month of the time the nearest competitor was opened
* Promo - indicates whether a store is running a promo on that day
* Promo2 - Promo2 is a continuing and consecutive promotion for some stores: 0 = store is not participating, 1 = store is participating
* Promo2Since[Year/Week] - describes the year and calendar week when the store started participating in Promo2
* PromoInterval - describes the consecutive intervals Promo2 is started, naming the months the promotion is started anew. E.g. "Feb,May,Aug,Nov" means each round starts in February, May, August, November of any given year for that store

---
## Data Cleaning

I made the following changes and created the following variables:

* Set NULL values “CompetitionDistance ” with mean data
* Set NULL values for “CompetitionOpenSinceMonth”, “CompetitionOpenSinceYear”, “Promo2SinceWeek”, “Promo2SinceYear” and “PromoInterval”
* Remove Data for stores which are close i.e “Open” = 0

---
## EDA

I looked at the distributions of the data and the value counts for the various categorical variables. Below are a few highlights :

![](https://github.com/SidSolanki28/Predict-Future-Product-Sales/blob/master/images/download.png)
![](https://github.com/SidSolanki28/Predict-Future-Product-Sales/blob/master/images/download%20(3).png)
![](https://github.com/SidSolanki28/Predict-Future-Product-Sales/blob/master/images/download%20(2).png)

---
## Model Building

### Facebook prophet
Prophet is a procedure for forecasting time series data based on an additive model where non-linear trends are fit with yearly, weekly, and daily seasonality, plus holiday effects. It works best with time series that have strong seasonal effects and several seasons of historical data. Prophet is robust to missing data and shifts in the trend, and typically handles outliers well.

##### Advantages:
* Open Source
* Accurate and fast
* Allows for a large number of people to make forecasts, possibly without training in time series methods;
* Tunable parameters
* Available for both Python and R

---
## Model Prediction
Facebook prophet model for store Id 10 to forecast its sales
![](https://github.com/SidSolanki28/Predict-Future-Product-Sales/blob/master/images/download%20(4).png)
![](https://github.com/SidSolanki28/Predict-Future-Product-Sales/blob/master/images/download%20(5).png)




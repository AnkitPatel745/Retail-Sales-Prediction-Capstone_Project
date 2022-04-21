![Rossoman](https://user-images.githubusercontent.com/88999980/164366292-ccfd231c-d575-4980-86ac-97b4ba71c10d.png)

# Retail-Sales-Prediction-Capstone_Project
Rossmann_Sales_Prediction_Capstone_Project ( Machine Learning - Regression )
### Problem Description
Rossmann operates over 3,000 drug stores in 7 European countries. Currently, Rossmann store managers are tasked with predicting their daily sales for up to six weeks in advance. Store sales are influenced by many factors, including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, the accuracy of results can be quite varied.
You are provided with historical sales data for 1,115 Rossmann stores. The task is to forecast the "Sales" column for the test set. Note that some stores in the dataset were temporarily closed for refurbishment.
### Data Description
Rossmann Stores Data.csv - historical data including Sales

store.csv - supplemental information about the stores

Data fields

Most of the fields are self-explanatory. The following are descriptions for those that aren't.

Id - an Id that represents a (Store, Date) duple within the test set

Store - a unique Id for each store

Sales - the turnover for any given day (this is what you are predicting)

Customers - the number of customers on a given day

Open - an indicator for whether the store was open: 0 = closed, 1 = open

StateHoliday - indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public holidays and weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None

SchoolHoliday - indicates if the (Store, Date) was affected by the closure of public schools

StoreType - differentiates between 4 different store models: a, b, c, d

Assortment - describes an assortment level: a = basic, b = extra, c = extended

CompetitionDistance - distance in meters to the nearest competitor store

CompetitionOpenSince[Month/Year] - gives the approximate year and month of the time the nearest competitor was opened

Promo - indicates whether a store is running a promo on that day

Promo2 - Promo2 is a continuing and consecutive promotion for some stores: 0 = store is not participating, 1 = store is participating

Promo2Since[Year/Week] - describes the year and calendar week when the store started participating in Promo2

PromoInterval - describes the consecutive intervals Promo2 is started, naming the months the promotion is started anew. E.g. "Feb,May,Aug,Nov" means each round starts in February, May, August, November of any given year for that store

## Hypothesis Mind Map
To better understand the relationship between the target variable (sales) and the features, I'll create some hypothesis based on the business problem to guide the feature engineering and then the exploratory data analysis.

In the EDA section, I'll validate these hypothesis and it'll let me have a good notion about the relation between the features and the target and it will help me to choose more accurately what feature to use when modeling.

However, before I do that, a mind map can be useful when creating all the hypothesis.![HypMindMap](https://user-images.githubusercontent.com/88999980/164365592-ec9db9eb-0355-4f3a-bdd8-e3b2cda81dd9.png)

### Hypothesis Creation
#### Store Hypothesis
Stores with more employees should sell more.

Stores with greater stock capacity should sell more.

Larger stores should sell more.

Stores with a larger assortment should sell more.

Stores with closer competitors should sell less.

Stores with longer competitors should sell more

#### Product Hypothesis
Stores that invest more in Marketing should sell more.

Stores with greater product exposure should sell more.

Stores with lower priced products should sell more.

Stores with more aggressive promotions (bigger discounts) should sell more.

Stores with active promotions for longer should sell more.

Stores with more promotion days should sell more.

Stores with more consecutive promotions should sell more.

#### Temporal Hypothesis
Stores open during the Christmas holiday should sell more.

Stores should be selling more over the years.

Stores should sell more in the second half of the year.

Stores should sell more after the 10th of each month.

Stores should sell less on weekends.

Stores should sell less during school holidays.

#### Hypothesis Final List
The next step is to choose which of them will be considered in the EDA section. The criterion I'll use is the availability of the corresponding feature. For instance, there's no data for number of employees or stock size, so, their corresponding hypothesis will not be considered.

This, the following hypothesis final list is created.

Stores with a larger assortment should sell more.

Stores with closer competitors should sell less.

Stores with longer competitors should sell more

Stores with active promotions for longer should sell more.

Stores with more promotion days should sell more.

Stores with more consecutive promotions should sell more.

Stores open during the Christmas holiday should sell more.

Stores should be selling more over the years.

Stores should sell more in the second half of the year.

Stores should sell more after the 10th of each month.

Stores should sell less on weekends.

Stores should sell less during school holidays.

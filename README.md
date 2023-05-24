# Walmart-Sales-Analysis-and-Forecasting
Walmart Sales Analysis and Forecasting


</div>

# <div align="center">Walmart store sales prediction</div>
<div align="center">

<img src  ="https://github.com/Pradnya1208/Walmart-store-sales-prediction/blob/main/output/intro.png?raw=true" width="100%">
</div>


## Objectives:
Data from Walmart stores accross the US is given, and it is up to us to forecast their weekly sales. The data is already split into a training and a test set, and we want to fit a model to the training data that is able to forecast those weeks sales as accurately as possible. In fact, our metric of interest will be the Mean Absolute Error.
## Dataset:
[Walmart - Store Sales Forecasting](https://www.kaggle.com/avelinocaio/walmart-store-sales-forecasting/data)

This is the historical sales data for 45 Walmart stores located in different regions. Each store contains a number of departments
In addition, Walmart runs several promotional markdown events throughout the year. These markdowns precede prominent holidays, the four largest of which are the Super Bowl, Labor Day, Thanksgiving, and Christmas. The weeks including these holidays are weighted five times higher in the evaluation than non-holiday weeks.

**stores.csv**:
This file contains anonymized information about the 45 stores, indicating the type and size of store.

**train.csv**:

This is the historical training data, which covers to 2010-02-05 to 2012-11-01. Within this file you will find the following fields:

- Store - the store number
- Dept - the department number
- Date - the week
- Weekly_Sales -  sales for the given department in the given store
- IsHoliday - whether the week is a special holiday week

**test.csv**:

This file is identical to train.csv, except we have withheld the weekly sales. You must predict the sales for each triplet of store, department, and date in this file.

**features.csv**:

This file contains additional data related to the store, department, and regional activity for the given dates. It contains the following fields:

- Store - the store number
- Date - the week
- Temperature - average temperature in the region
- Fuel_Price - cost of fuel in the region
- MarkDown1-5 - anonymized data related to promotional markdowns that Walmart is running. MarkDown data is only available after Nov 2011, and is not available for all stores all the time. Any missing value is marked with an NA.
- CPI - the consumer price index
- Unemployment - the unemployment rate
- IsHoliday - whether the week is a special holiday week

For convenience, the four holidays fall within the following weeks in the dataset (not all holidays are in the data):

- Super Bowl: 12-Feb-10, 11-Feb-11, 10-Feb-12, 8-Feb-13
- Labor Day: 10-Sep-10, 9-Sep-11, 7-Sep-12, 6-Sep-13
- Thanksgiving: 26-Nov-10, 25-Nov-11, 23-Nov-12, 29-Nov-13
- Christmas: 31-Dec-10, 30-Dec-11, 28-Dec-12, 27-Dec-13
## Implementation:

**Libraries:** `sklearn` `Matplotlib` `pandas` `seaborn` `NumPy` 
## A few glimpses of EDA:
In this section, we will explore the datasets provided, join information between some of them and make relevant transformations.

#### Holiday Analysis:
We will analyze the week days that the Holidays fall on each year. This is relevant to know how many pre-holiday days are inside each Week marked as 'True' inside 'IsHoliday' field.

If, for a certain Week, there are more pre-holiday days in one Year than another, then it is very possible that the Year with more pre-holiday days will have greater Sales for the same Week. So, the model will not take this consideration and we might need to adjust the predicted values at the end.

Another thing to take into account is that Holiday Weeks but with few or no pre-holiday days might have lower Sales than the Week before.

We can use SQL, putting the week days for each Holiday in every year. Doing some research, the Super Bowl, Labor Day and Thanksgiving fall on the same day. In the other hand, Christmas is always on December 25th, so the week day can change.

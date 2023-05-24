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

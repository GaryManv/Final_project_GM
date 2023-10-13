# Final_project_GM

# Goal
Create most accurate product demand forecasting model to optimize inventory level aiming to reduce stockouts and holding costs 

# Step 1 : Data observation and cleaning
Found and handle missing data, zeros , non-proper data types. Negative data were in brackets which was challenging in terms of data type transformation.Negative values in Order_Demand column were removed, most of them with their possitive pairs (probably returns from customers)


# Step 2: EDA
The original data has been transformed so that each column corresponds to a specific product. After pivoting, all columns with NaN and zero values have been removed.
Visualizations didn't show any clear trend or pattern.
Data was split into stationary and non-stationary datasets. Splitting is important because different approaches (ARIMA and SARIMAX) are used for different datasets. The split datasets were further divided into training and testing datasets with an 80/20 proportion.

# Step 3: pdq hyperparameters tuning for ARIMA
To obtain the pdq parameters for the stationary dataset, I iterated through all possible pdq variants for all products and select only those with a small error, in my case, 10%. As a result, I obtained a list of products with their corresponding optimal pdq-s.

# Step 4: ARIMA model
As a result of applying ARIMA model I got a dataset with 6 month forecast.

# Step 5: pdq hyperparameters tuning for SARIMAX
The process of getting hyperparameters for SARIMAX model is IDENTICAL to ARIMA except that the other dataset is used.

# Step 6: SARIMAX model
The result calculation for Sarimax is similar to ARIMA, except that there is a new parameter “s” for seasonality in Sarimax

# Results / Challenges:
*  Arima and Sarimax models demonstrate positive performance and can provide a 10% improvement in forecast accuracy compared to a simple naive forecast.

*  Despite positive performance, the models gave accurate results for only 30% of the products.

** Hyperparameters tuning required big amount of time. 
** ARIMA [580 items] : Elapsed time: 5 hours 
** SARIMAX  [180 items] : Elapsed time: 57 hours

# Future Goals
** Implementation of Models on the Provided Time Series Dataset

1.  Random Forest Model
2.  XGBoost Model
3.  Multivariate Time Series Analysis


# Brainstorm 
Divide into "predictible" and "non predictible" products / categories. Filter/exclude non-predictible ones.
Find reasons for non-predictibility
Which are most returned products? Which are warehouses with most returns?




# Time Series Analysis and Forecasting of Household Power Consumption 

Electricity power consumption forecasting has become increasingly important in present-day electrical power management systems. The project aims to develop and compare models for forecasting time series data on household electricity consumption using SARIMA, LSTM, linear regression and random forest. The selection of the optimal forecasting model is based on some metrics like RMSE, R2 score and MAPE.

## Feature Extraction and Preprocessing
* The two columns ‘Date’ and ‘Time’ of the type ‘string’ are converted into one column of the type 'DateTime' and set as index.

* The data included some missing values and character ‘?’ as strings. Both have been converted to ‘nan’ while importing the dataset and imputed as mean.

* Initialized low_memory=False to avoid warnings because of the presence of ‘?’ values.
* Energy consumption is calculated using the formula: global_active_power*1000/60 - sub_metering_1 - sub_metering_2 - sub_metering_3. It represents the active energy consumed
every minute (in watt hour) in the household by electrical equipment not measured in submeterings 1, 2 and 3.

* Resampled the dataset with a frequency of 15 days. 

## Models
1. SARIMA
2. Linear Regression
3. Random Forest
4. LSTM

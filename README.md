<h1><p align='center'> Time Series Analysis and Forecasting of Household Power Consumption</p></h1> 

Electricity power consumption forecasting has become increasingly important in present-day electrical power management systems. The project aims to develop and compare models for forecasting time series data on household electricity consumption using SARIMA, LSTM, linear regression and random forest. The selection of the optimal forecasting model is based on some metrics like RMSE, R2 score and MAPE.

Dataset description: http://archive.ics.uci.edu/ml/datasets/Individual+household+electric+power+consumption


## Data Dictionary 

| Column   Position 	| Atrribute Name        	| Definition                                                                                                                                                                                                              	| Data Type    	| Example                          	| % Null Ratios 	|
|-------------------	|-----------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|--------------	|----------------------------------	|---------------	|
| 1                 	| Date                  	| Date: Date in   format dd/mm/yyyy                                                                                                                                                                                       	| Quantitative 	| 16/12/2006, 10/5/2007, 24/9/2007 	| ?             	|
| 2                 	| Time                  	| Time: time in   format hh:mm:ss                                                                                                                                                                                         	| Quantitative 	| 17:27:00, 6:56:00, 10:00:00      	| ?             	|
| 3                 	| Global_Active_Power   	| Global_active_power:   Household global minute-averaged active power (in kilowatt)                                                                                                                                      	| Quantitative 	| 4.216, 5.412, 3.488              	| ?             	|
| 4                 	| Global_Reactive_Power 	| Global_reactive_power:   Household global minute-averaged reactive power (in kilowatt)                                                                                                                                  	| Quantitative 	| 0.418, 0.47, 0.228               	| ?             	|
| 5                 	| Voltage               	| Voltage:   Minute-averaged voltage (in volt)                                                                                                                                                                            	| Quantitative 	| 234.84, 232.78, 233.06           	| ?             	|
| 6                 	| Global_Intensity      	| Global_intensity:   Household global minute-averaged current intensity (in ampere)                                                                                                                                      	| Quantitative 	| 18.4, 23.2, 15                   	| ?             	|
| 7                 	| Sub_Metering_1        	| Sub_metering_1:   Energy sub-metering No. 1 (in watt-hour of active energy). It corresponds to   the kitchen, containing mainly a dishwasher, an oven and a microwave (hot   plates are not electric but gas powered).  	| Quantitative 	| 1, 38, 17                        	| ?             	|
| 8                 	| Sub_Metering_2        	| Sub_metering_2:   Energy sub-metering No. 2 (in watt-hour of active energy). It corresponds to   the laundry room, containing a washing-machine, a tumble-drier, a   refrigerator and a light.                          	| Quantitative 	| 1, 36, 5                         	| ?             	|
| 9                 	| Sub_Metering_3        	| Sub_metering_3:   Energy sub-metering No. 3 (in watt-hour of active energy). It corresponds to   an electric water-heater and an air-conditioner                                                                        	| Quantitative 	| 17, 0, 18                        	| ?             	|

Note: 
(global_active_power*1000/60 - sub_metering_1 - sub_metering_2 - sub_metering_3) represents the active energy consumed every minute (in watt hour) in the household by electrical equipment not measured in sub-meterings 1, 2 and 3

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

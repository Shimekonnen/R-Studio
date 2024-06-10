# R-Studio Forecasting

## Project Overview
The R Studio analysis aims to provide insights into the call volume of a service desk by forecasting future call volumes. By analyzing forecasts and trends, data-driven recommendations can be made to enhance workforce management. The forecasting process considers past call volume, seasonality, workforce capacity, and other relevant factors.

## Data Sources
Call Volume Data: The primary dataset used for this analysis is a .csv file containing detailed information about the call volumes received by the service desk over a specified period.

## Tools
SQL Server: Used for data analysis.<br/>
Tableau: Used for creating a report. <br/>
R Studio: Used for forecasting.<br/>
Excel: Used for data cleaning.<br/>

## Data Cleaning and Preparation
In the initial phase, the following tasks were performed:

Data loading and inspection.<br/>
Handling missing values.<br/>
Data Analysis<br/>
sql<br/>

## R Script
call.Volume.data <- read.csv("C:\\Users\\x\\Desktop\\Call Forecasting (Monthly)\\call_Volume_data.csv") <br/>
call.Volume.data<br/>
call.Volume.dara$Call_MONTH = as.Date(call.Volume.data$Call_MONTH, "%m/%d/%Y")<br/>
Hist_ts = ts(call.Volume.data$Call_count, frequency = 12)<br/>
Hist_ts<br/>
Hist_ts_wh_m = HoltWinters(Hist_ts, seasonal = "multiplicative")<br/>
Hist_ts_wh_pr_m = predict(Hist_ts_wh_m, 12)<br/>
Hist_ts_wh_pr_m<br/>

# R Script Summary
This R script reads the call volume data from a CSV file, converts the date column to the appropriate format, and creates a time series object from the call count data. It then applies the Holt-Winters method to perform a seasonal forecast with multiplicative seasonality. The script predicts the call volumes for the next 12 months and saves the R script history.
## Results
Enhanced workforce management by aligning staff schedules with predicted call volumes.

![image](https://github.com/Shimekonnen/R-Studio/assets/128651580/38035838-cbe0-4251-967b-a8c1380ddc04)

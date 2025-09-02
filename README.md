# Time Series Analysis of Air Passengers Traffic

This project performs a time series analysis and forecasting on the classic "Air Passengers" dataset. The goal is to understand the underlying patterns in the passenger traffic data, handle any non-stationary characteristics, and build a predictive model to forecast future passenger numbers.

## Dataset
The analysis uses the `airline-passenger-traffic.csv` dataset, which contains monthly international airline passenger numbers from 1949 to 1960.

**Columns:**
- `Month`: The date of the observation  
- `Passengers`: The number of international airline passengers (in thousands) for that month  

## Methodology
1. **Data Pre-processing**: Missing values were handled using linear interpolation. Outlier detection was performed and no significant outliers were found.  
2. **Exploratory Data Analysis (EDA)**:  
   - Clear upward trend over the years  
   - Strong yearly seasonality (period = 12)  
   - Increasing variance (heteroscedasticity)  
3. **Stationarity**: The series was non-stationary (confirmed via ADF and KPSS tests). A log transformation was applied to stabilize variance, followed by seasonal differencing (lag 12).  
4. **Model Fitting**: A SARIMAX model was used with grid search to find the best parameters.  

## Best Model and Results
- **Order (p,d,q):** (0, 1, 1)  
- **Seasonal (P,D,Q,s):** (1, 1, 1, 12)  
- **Performance:**  
  - MAPE: 4.09%  

This model provided the most accurate forecasts, capturing both the increasing trend and strong annual seasonality.

## Forecasting
The final model successfully forecasts passenger numbers, aligning well with both the training and test data, and provides a reliable prediction of future airline passenger traffic.

Time Series Analysis of Air Passengers Traffic
This project performs a time series analysis and forecasting on the classic "Air Passengers" dataset. The goal is to understand the underlying patterns in the passenger traffic data, handle any non-stationary characteristics, and build a predictive model to forecast future passenger numbers.

Dataset
The analysis uses the airline-passenger-traffic.csv dataset, which contains monthly international airline passenger numbers from 1949 to 1960.

Columns:

Month: The date of the observation.

Passengers: The number of international airline passengers (in thousands) for that month.

Methodology
The analysis follows a standard time series forecasting workflow:

Data Pre-processing: Missing values in the dataset were handled using linear interpolation, which proved to be a better fit for the data's trend and seasonality compared to mean imputation. Outlier detection was also performed, and no significant outliers were found.

Exploratory Data Analysis (EDA): The time series was decomposed to identify its components:

Trend: The data shows a clear upward trend over the years.

Seasonality: A strong, repeating seasonal pattern is visible, with a period of 12 months (one year).

Heteroscedasticity: The variance of the time series increases over time.

Stationarity: The series was confirmed to be non-stationary through both visual inspection and statistical tests (Augmented Dickey-Fuller and KPSS). To address this, a log transformation was applied to stabilize the variance, followed by a seasonal differencing with a lag of 12 to remove the trend and seasonality.

Model Fitting: A Seasonal AutoRegressive Integrated Moving Average with eXogenous factors (SARIMAX) model was used for forecasting. A grid search was performed to find the optimal (p, d, q) and seasonal (P, D, Q, s) orders for the model.

Best Model & Results
The best-performing SARIMAX model was determined based on the lowest RMSE and MAPE values from the grid search.

Best Model:

Order (p, d, q): (4, 1, 1)

Seasonal Order (P, D, Q, s): (1, 1, 1, 12)

Performance Metrics:

RMSE: 0.0787

MAPE: 1.18%

This model provided the most accurate forecasts on the test data, minimizing both the root mean squared error and the mean absolute percentage error.

Forecasting
The plot below shows the performance of the final model, comparing the forecasted values with the original training and testing data.

The model successfully captures the increasing trend and the annual seasonal fluctuations of the passenger data, providing a reliable forecast.

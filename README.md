# Forecasting Daily Bike Rental Demand Using Seasonal ARIMA

## Project Overview

This project applies time series modelling techniques in R to forecast daily bike rental demand using the Capital Bikeshare dataset (2011–2012).

The objective was to explore temporal patterns in rental activity and develop a statistically sound forecasting model capable of generating short-term predictions.

---

## Dataset

- Source: UCI Machine Learning Repository  
- Observations: 731 daily records  
- Time Period: 2011–2012  
- Target Variable: `cnt` (total daily bike rentals)

The dataset includes weather variables, seasonal indicators, and calendar features alongside total rental counts.

---

## Tools and Libraries

- R  
- tidyverse  
- tsibble  
- feasts  
- fable  
- ggtime  

---

## Methodology

The project followed a structured time series analysis workflow:

1. **Data Preparation**
   - Converted the dataset into a `tsibble` object for time-aware operations.
   - Verified date indexing and structure.

2. **Exploratory Analysis**
   - Visualised daily rental demand.
   - Identified upward trend and strong weekly seasonality.

3. **Decomposition**
   - Applied STL decomposition to separate trend, seasonality, and residual components.
   - Confirmed stable weekly seasonal behaviour.

4. **Stationarity Assessment**
   - Examined autocorrelation (ACF) to evaluate non-stationarity.
   - Identified need for first differencing.

5. **Model Development**
   - Fitted a seasonal ARIMA model.
   - Selected model: **ARIMA(1,1,1)(1,0,2)[7]**
     - `d = 1` removes long-term trend
     - `[7]` captures weekly seasonality
     - `D = 0` indicates stable seasonal structure

6. **Model Diagnostics**
   - Evaluated residual plots and autocorrelation.
   - Confirmed residuals behave approximately as white noise.

7. **Forecasting**
   - Generated a 30-day forecast.
   - Observed preserved weekly patterns with widening prediction intervals reflecting uncertainty.

---

## Key Findings

- Bike rental demand exhibits strong weekly seasonality.
- A clear upward trend exists across the two-year period.
- First differencing was required to achieve stationarity.
- The selected ARIMA model adequately captures both trend and seasonal dynamics.
- Forecast uncertainty increases with horizon length, as expected in time series modelling.

---

## Repository Contents

- `Forecasting_Daily_Bike_Rental_Demand.Rmd`
- `Forecasting_Daily_Bike_Rental_Demand.html`
- `day.csv`

---

## Conclusion

This project demonstrates a diagnostic-driven approach to time series forecasting, progressing from exploratory analysis to model validation and forecasting. The final ARIMA model provides realistic short-term projections while maintaining statistical rigor and interpretability.

---

# HW-10-Time-Series
**Unit 10 - A Yen for the Future**

## The Scenario

The financial departments of large companies often have to make foreign currency transactions when doing international business, while hedge funds are also interested in anything that will provide an edge in predicting currency movements. Hence, both are always eager to gain a better understanding of the future direction and risk of various currencies.

In this assignment, I have tested the many time series tools that I have learnt in order to predict future movements in the value of the Canadian dollar versus the Japanese yen.

## Navigating the GitHub

The following was provided at the beginging of the assessment and can be found in the Starter_code folder:

- [Time-Series Starter Notebook](https://github.com/RaelynSangil/HW-10-Time-Series/blob/a31665b343453e45e61d0c8e91965a7f480c834f/Starter_Code/time_series_analysis.ipynb)
- [Linear Regression Starter Notebook](https://github.com/RaelynSangil/HW-10-Time-Series/blob/a31665b343453e45e61d0c8e91965a7f480c834f/Starter_Code/regression_analysis.ipynb)
- [CAD/JPY Data CSV File](https://github.com/RaelynSangil/HW-10-Time-Series/blob/a31665b343453e45e61d0c8e91965a7f480c834f/Starter_Code/cad_jpy.csv)

In the Worked_Code folder you will find:

- [Image Folder](https://github.com/RaelynSangil/HW-10-Time-Series/tree/main/Worked_Code/Image) - Contains images of all the plots created in the ipynb files.
- [Time Series Analysis](https://github.com/RaelynSangil/HW-10-Time-Series/blob/05a1df497e87a15cbe516161b0563fa11628a30b/Worked_Code/regression_analysis.ipynb) - The code I have written for this notebook.
- [Linear Regression Analysis](https://github.com/RaelynSangil/HW-10-Time-Series/blob/05a1df497e87a15cbe516161b0563fa11628a30b/Worked_Code/regression_analysis.ipynb) - This has currently not been filled in.

## Important Notice

1. Please view this github in Day Theme - Light Default so that headers and axises on the plots show.
2. During the process of writing this code, a deprication that occured with statsmodels library caused issues with the ARMA model.[<sup>1</sup>](#reference-list)
3. At this point, the Linear Regression Analysis of this assessment has not been completed.

## Time Series Analysis

### Initial Time-Series Plotting

<ins> CAD/JPY Exchange Rates </ins>

![CAD/JPY Exchange Rates](https://github.com/RaelynSangil/HW-10-Time-Series/blob/a6b881ec7a2951b3c816e81172922e72f163a0ae/Worked_Code/Image/CADorJPY_Exchange_Rates_plot.png)

**Question:** Do you see any patterns, long-term and/or short?

**Answer:** Ever since 1995, there looks to be a 4 year trend. This trend looks like the prices will go up and then drop again towards the end of the 4 year mark.

### Decomposition Using Hodrick-Prescott Filter

<ins> CAD Price vs. Trend </ins>

![CAD Price vs. Trend](https://github.com/RaelynSangil/HW-10-Time-Series/blob/a6b881ec7a2951b3c816e81172922e72f163a0ae/Worked_Code/Image/CAD_Price_vs._Trend_plot.png)

**Question:** Do you see any patterns, long-term and/or short?

**Answer:** The price tends to follow the trend, with the price currently expected to rise. However, there also seems to be a trend where the price dips before or just after the start of a year. It is rising at this point, because it recently fell at the start of 2020.

<ins> Noise </ins>

![Noise](https://github.com/RaelynSangil/HW-10-Time-Series/blob/a6b881ec7a2951b3c816e81172922e72f163a0ae/Worked_Code/Image/Noise_plot.png)

### Forecasting Returns using an ARMA Model

Please refer to Important Notice 2. [<sup>IN2</sup>](#important-notice)

<ins> 5 Day Returns Forecast </ins>

![5 Day Returns Forecast](https://github.com/RaelynSangil/HW-10-Time-Series/blob/a6b881ec7a2951b3c816e81172922e72f163a0ae/Worked_Code/Image/5_Day_Returns_Forecast_plot.png)

**Question:** Based on the p-value, is the model a good fit?

**Answer:** Based on the P-value for the second AR, the model is not a good fit since p > 0.05.

### Forecasting the Exchange Rate Price using an ARIMA Model

<ins> 5 Day Futures Price Forecast </ins>

![5 Day Futures Price Forecast](https://github.com/RaelynSangil/HW-10-Time-Series/blob/a6b881ec7a2951b3c816e81172922e72f163a0ae/Worked_Code/Image/5_Day_Future_Price_Forecast_plot.png)

**Question:** What does the model forecast will happen to the Japanese Yen in the near term?

**Answer:** The Arima model forecasts that the Japanse Yes price will fall in the near term.

### Volatility Forecasting with GARCH

<ins> 5 Day Forecast of Volatility </ins>

![5 Day Forecast of Volatility](https://github.com/RaelynSangil/HW-10-Time-Series/blob/a6b881ec7a2951b3c816e81172922e72f163a0ae/Worked_Code/Image/5_Day_Forecast_of_Volatility_plot.png)

**Question:** What does the model forecast will happen to volatility in the near term?

**Answer:** Volatility will increase.

### Time Series Analysis Conclusions

1. **Based on your time series analysis, would you buy the yen now?**

- No.

2. **Is the risk of the yen expected to increase or decrease?**

- Increase.

3. **Based on the model evaluation, would you feel confident in using these models for trading?**

- No as p > 0.05

## Linear Regression Analysis

### Make predictions using the Testing Data

<ins> First 20 Predictions </ins>

![First 20 Predictions](https://github.com/RaelynSangil/HW-10-Time-Series/blob/69915cfde66e870bff5f4f103ff333eb3be58cf2/Worked_Code/Image/First_20_Predictions.PNG)

### Performance

- Out-of-Sample Root Mean Squared Error (RMSE): 0.6445805658569028
- In-sample Root Mean Squared Error (RMSE): 0.841994632894117

### Linear Regression Analysis Conclusions

**Question:** Does this model perform better or worse on out-of-sample data as compared to in-sample data?

**Answer:** The in-sample RMSE is higher than the out of sample RMSE, so the out of sample RMSE performed bette.

# Reference List
- [<sup>1</sup> https://www.statsmodels.org/v0.12.0/generated/statsmodels.tsa.arima_model.ARMA.html](https://www.statsmodels.org/v0.12.0/generated/statsmodels.tsa.arima_model.ARMA.html)
# Apple Inc. Stock Market Forecasting

## Introduction
This project focuses on forecasting the stock market prices of Apple Inc. using historical data obtained from Yahoo Finance. The forecasting aims to provide insights into future price movements, assisting investors and analysts in making informed decisions.
## Data Source
The dataset spans from January 2, 2020, to June 15, 2025, and is sourced from Yahoo Finance. This period includes both pre-pandemic and post-pandemic market conditions, allowing for a comprehensive analysis of Apple Inc.'s stock behavior over time. This dataset contains several columns including date (Date), opening price (Open), low price (Low), high price (High), closing price (Close), and stock volume (Volume).
![image](https://github.com/user-attachments/assets/ee4b9c28-b9c6-4334-84fe-3e10f6f8a8fe)

![image](https://github.com/user-attachments/assets/7e920ceb-db90-474e-bbc2-17a6ae54322e)

![image](https://github.com/user-attachments/assets/8084fa71-c8ee-4db0-9547-ef74e69345ff)

## Data Cleansing
The dataset contains 622 missing dates, which can pose challenges for effective time series stock forecasting. To address this issue, we have decided to replace the missing values with the most recent available data from the preceding date. This approach helps maintain the continuity of the time series and ensures a more accurate forecasting model.
## Analysis
We create another column in our dataset which Daily Return to evaluate stock performance and understanding market behavior.
- Expected Return: 0.0006

The daily return of the stock is approximately 0.06% per day, which suggests a potential for profit, though modest.
- Risk (Standard Deviation): 0.0171

A standard deviation of 0.0171 means that daily returns typically fluctuate by about 1.71% around the average daily return.

Investors should weigh the expected return against the risk before making investment decisions. Higher potential returns usually come with higher risk.

![image](https://github.com/user-attachments/assets/dc4465e9-e28f-4fd9-a659-e904face23ff)

The histogram consists of orange bars, which represent the frequency distribution of daily returns. The distribution appears to be negatively skewed, with most daily returns clustered around zero, indicating that the stock's returns are predominantly small and close to the mean. A few outliers exist on the left side, suggesting occasional larger negative returns, but the frequency of these occurrences is low.

## Data Modelling





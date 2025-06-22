# Apple Inc. Stock Market Forecasting

## Introduction
This project focuses on forecasting the stock market prices of Apple Inc. using historical data obtained from Yahoo Finance. The forecasting aims to provide insights into future price movements, assisting investors and analysts in making informed decisions.
## Data Source
The dataset spans from January 2, 2020, to June 15, 2025, and is sourced from Yahoo Finance. This period includes both pre-pandemic and post-pandemic market conditions, allowing for a comprehensive analysis of Apple Inc.'s stock behavior over time. This dataset contains several columns including date (Date), opening price (Open), low price (Low), high price (High), closing price (Close), and stock volume (Volume).

![image](https://github.com/user-attachments/assets/ef71d18a-01d2-4fb0-b96d-20c9f25c580d)


![image](https://github.com/user-attachments/assets/7e920ceb-db90-474e-bbc2-17a6ae54322e)


![image](https://github.com/user-attachments/assets/8084fa71-c8ee-4db0-9547-ef74e69345ff)

## Data Cleansing
The dataset contains 622 missing dates, which can pose challenges for effective time series stock forecasting. To address this issue, we have decided to replace the missing values with the most recent available data from the preceding date. This approach helps maintain the continuity of the time series and ensures a more accurate forecasting model.
## Analysis
We create another column in our dataset which Daily Return to evaluate stock performance and understanding market behavior.
- Expected Return: 0.0006

> The daily return of the stock is approximately 0.06% per day, which suggests a potential for profit, though modest.

- Risk (Standard Deviation): 0.0171

> A standard deviation of 0.0171 means that daily returns typically fluctuate by about 1.71% around the average daily return.

Investors should weigh the expected return against the risk before making investment decisions. Higher potential returns usually come with higher risk.

![image](https://github.com/user-attachments/assets/dc4465e9-e28f-4fd9-a659-e904face23ff)

The daily returns fluctuate widely, with many returns close to zero, indicating that the stock has a high level of volatility. The presence of spikes (both positive and negative) suggests that the stock experiences significant price changes on some days.

The histogram shows that most daily returns are clustered around zero, with few extreme values. The distribution appears to be slightly skewed, with some negative returns but a significant number of returns that are very close to zero. The high frequency of returns around zero indicates that the stock tends to have small daily movements rather than large swings.

## Modelling
**1. Data Preparation**
- Scale the 'Close' prices to a range of 0 to 1 with MinMaxScaler for better model performance.
- Create sequence
- Reshapes the input data into the format [samples, time steps, features], which is required for LSTM networks.
- The dataset is split into training and testing sets using train_test_split, with 10% of the data reserved for testing.
  
**2. Building the LSTM Model**
- Architecture:
  The model is sequential, composed of:
  + An LSTM layer with 64 units, returning sequences for stacking.
  + A dropout layer (20%) to prevent overfitting.
  + A second LSTM layer with 32 units, not returning sequences.
  + Another dropout layer (10%).
  + A dense layer producing a single output (the predicted price).
- Compilation: Uses the Adam optimizer and mean squared error as the loss function.
- Training the Model: The model is trained on the training set for 100 epochs with a batch size of 32.
  
**3. Make Prediction**
- Predictions are made on the test set.
- The predicted values are inverse-transformed to revert back to the original price scale.
  
**4. Evaluation Metrics**
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- R² Score (coefficient of determination)
## Result
After training model and making prediction on the test set, we got result as below:
![image](https://github.com/user-attachments/assets/8a9ce5d8-680a-46c8-abe0-c89695b634bd)

- Mean Absolute Error: 3.10
> On average, the model's predictions deviate from the actual closing prices by approximately $3.10.
- Mean Squared Error: 22.25
> The average of the squared differences between predicted and actual values is 22.25.
- R^2 Score: 0.94
> The R² score indicates that 94% of the variance in the actual closing prices can be explained by the model's predictions.

The model demonstrates high accuracy in predicting stock prices, as indicated by the MAE, MSE, and R² score. The close alignment seen in the graph reinforces the effectiveness of the LSTM model in capturing price movements. We decide to use this model to forecast the stock price in the next 60 days and the result we get is the stock price will gradually rise in the next 2 months as below.

![image](https://github.com/user-attachments/assets/c725da7e-ace5-48a6-abc2-27c7f6c2fa9c)

![image](https://github.com/user-attachments/assets/f45f9fa5-470c-4739-aec3-f5b5a8d91736)   ![image](https://github.com/user-attachments/assets/f1e89936-1840-4777-827c-8fdbb348384e)

## Conclusion

The evaluation metrics indicate that the model is highly effective in predicting stock prices. With a Mean Absolute Error (MAE) of $3.10, the model's predictions are consistently close to the actual closing prices. The Mean Squared Error (MSE) of 22.25 further demonstrates its ability to minimize prediction errors, while the R² score of 0.94 shows that the model explains 94% of the variance in actual prices, highlighting its robustness.

Given the model's high accuracy and the strong alignment between predicted and actual prices, we have decided to utilize this LSTM model to forecast stock prices over the next 60 days. The results suggest a gradual increase in stock prices during this period, indicating potential positive trends for investors. This model can thus serve as a reliable tool for making informed investment decisions.










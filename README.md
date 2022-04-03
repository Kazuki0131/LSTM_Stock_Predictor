# LSTM_Stock_Predictor
- - -

## Background

Due to the volatility of cryptocurrency speculation, investors will often try to incorporate sentiment from social media and news articles to help guide their trading strategies. One such indicator is the Crypto Fear and Greed Index (FNG) which attempts to use a variety of data sources to produce a daily FNG value for cryptocurrency. You have been asked to help build and evaluate deep learning models using both the FNG values and simple closing prices to determine if the FNG indicator provides a better signal for cryptocurrencies than the normal closing price data.

In this assignment, you will use deep learning recurrent neural networks to model bitcoin closing prices. One model will use the FNG indicators to predict the closing price while the second model will use a window of closing prices to predict the nth closing price.

## Prepare data for training and testing
* I used the FNG values to try and predict the closing price for the Fear and Greed model and used previous closing prices to try and predict the next clsoing price for the closing price model.
* Each model used 70% of the data for training and 30% of the data for testing.
* MinMaxScaler was used to the X and y values to scale the data for the model.
* I reshpaed the X_train and X_test values to fit the model's requirement of samples, time steps, and features.

## Build and train customer LSTM RNNs
The same custom LSTM RNN  architecture was used. The FNG values data was used to train the Fear and Greed model. The previous closing prices data was used to train the closing price model.

In order to compare each model accurately, I used the same parameters below and training steps are used for each model.
* epochs = 60
* batch size = 1
* drop fraction = 0.2

## Evaluate the performance of each model

* The closing price model has a lower loss the Fear and Greed model.
* The closing price model tracks the actual values better over time.
* 5 days window works best for the closing price model. 1 day window works best for the Fear and Greed model.

|    | loss (closing price model) | loss (Fear and Greed model |
|----|:--------------------------:|:--------------------------:|
|10 days window | 0.0124 | 0.1311 |
|5 days window | 0.0185 | 0.1258 |
|1 day window | 0.0195 | 0.1100 |
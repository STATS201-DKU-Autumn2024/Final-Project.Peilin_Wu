# Overview
This project provides an integrated machine learning pipeline which can predict Bitcoin prices using a combination of diffusion models for noise handling and Long Short-Term Memory (LSTM) models for time series forecasting. The model is designed to provide investment suggestions, advising whether to take a long or short position in Bitcoin based on its predicted price movements to reach a low fluctuation. Key tasks include data collection, preprocessing, model training, and generating investment advice.
# Files Included
‘’‘
Untitled24.ipynb
‘’‘
This is the main notebook that includes the following components:

Data Collection and Preprocessing: Loading and processing Bitcoin price data along with sentiment analysis data (if available).
Diffusion Model: A diffusion model to denoise the price data.
LSTM Model: A Long Short-Term Memory model for time series prediction of Bitcoin prices.
Training and Evaluation: Code to train the models and output predictions and suggestions for investment strategies.
Data/bitcoin0.csv
Contains historical Bitcoin price data including time, open, close, high, low prices, and volumes.

Data/google trends/geoMapbitcoin.csv 
Contains sentiment data based on Google Trends for Bitcoin, used for enhancing predictions.


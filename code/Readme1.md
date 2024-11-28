# Overview
This project provides an integrated machine learning pipeline which can predict Bitcoin prices using a combination of diffusion models for noise handling and Long Short-Term Memory (LSTM) models for time series forecasting. The model is designed to provide investment suggestions, advising whether to take a long or short position in Bitcoin based on its predicted price movements to reach a low fluctuation. Key tasks include data collection, preprocessing, model training, and generating investment advice.

# Files Included
Untitled24.ipynb\
This is the main notebook that includes the following components:

Data Collection and Preprocessing: Loading and processing Bitcoin price data along with sentiment analysis data.\
Diffusion Model: A diffusion model to denoise the price data.\
LSTM Model: A Long Short-Term Memory model for time series prediction of Bitcoin prices.\
Training and Evaluation: Code to train the models and output predictions and suggestions for investment strategies.\
Data/bitcoin0.csv\
Contains historical Bitcoin price data including time, open, close, high, low prices, and volumes.\

Data/google trends/geoMapbitcoin.csv \
Contains sentiment data based on Google Trends for Bitcoin, used for enhancing predictions.

# Prerequisites
To run this code, you need to have the following libraries installed:

* Python 3.9 or higher
* pandas (for data manipulation)
* numpy (for numerical operations)
* sklearn (for machine learning utilities)
* torch (for deep learning models)
* matplotlib (for visualizations)

You can install all dependencies using the following command:\
pip install -r requirements.txt\
Where requirements.txt contains:\
pandas==1.3.3\
numpy==1.21.0\
scikit-learn==0.24.2\
torch==1.9.0\
matplotlib==3.4.3

# Usage Instructions
## Step 1: Loading Datasets
To load the Bitcoin price data, run the following code:
```import pandas as pd

price_data_url = 'https://raw.githubusercontent.com/STATS201-DKU-Autumn2024/Problem_Set_1.Peilin_Wu/refs/heads/main/Data/bitcoin0.csv'
price_df = pd.read_csv(price_data_url)
price_df['time'] = pd.to_datetime(price_df['time'], unit='ms')
price_df.set_index('time', inplace=True)
price_df = price_df[['close', 'high', 'low', 'open', 'volumefrom', 'volumeto']]




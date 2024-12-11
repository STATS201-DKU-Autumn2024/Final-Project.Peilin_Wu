# Overview
This project provides an integrated machine learning pipeline which can predict Bitcoin prices using a combination of diffusion models for noise handling and transformer models for time series forecasting. The model is designed to provide investment suggestions, advising whether to take a long or short position in Bitcoin based on its predicted price movements to reach a low fluctuation. Key tasks include data collection, preprocessing, model training, and generating investment advice.

# Files Included
code_of_the_model.ipynb\
This is the main notebook that includes the following components:

Data Collection and Preprocessing: Loading and processing Bitcoin price data along with sentiment analysis data.\
Diffusion Model: A diffusion model to denoise the price data.\
Transformer Model: A transformer model for time series prediction of Bitcoin prices.\
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
You can access to the notebook at links shown below:
* Full codes (showing the evolution of the code):https://colab.research.google.com/drive/102viRpUAZXn4sVcTeXF4fEO4BzIhpr4J#scrollTo=5L8uMWnnaIJu
* code_of_the_model (shown in the GitHub):https://colab.research.google.com/drive/12wYhOwULbY5AypTgHcR9N4Uur_dmVOuG?authuser=0#scrollTo=VUyb8nR_q0kh
## Step 1: Loading Datasets
To load the Bitcoin price data, run the following code:
```
import pandas as pd
price_data_url = 'https://raw.githubusercontent.com/STATS201-DKU-Autumn2024/Problem_Set_1.Peilin_Wu/refs/heads/main/Data/bitcoin0.csv'
price_df = pd.read_csv(price_data_url)
price_df['time'] = pd.to_datetime(price_df['time'], unit='ms')
price_df.set_index('time', inplace=True)
price_df = price_df[['close', 'high', 'low', 'open', 'volumefrom', 'volumeto']]
```
For market sentiment data (if available), load it as follows:
```
sentiment_data_url = 'https://raw.githubusercontent.com/STATS201-DKU-Autumn2024/Problem_Set_1.Peilin_Wu/refs/heads/main/Data/google%20trends/geoMapbitcoin.csv'
sentiment_df = pd.read_csv(sentiment_data_url)
```
## Step 2: Running NLP or Social Network Analysis
If sentiment analysis is included, preprocess the sentiment data before integrating it into the model. Use any NLP techniques such as tokenization or sentiment analysis (e.g., using TextBlob or transformers library).

## Step 3: Training and Evaluating Predictive Models
Run the diffusion model to denoise the data:
```
import torch
import torch.nn as nn
import torch.optim as optim

# Diffusion model code (as defined in the notebook) goes here
```
Train the transformer model:
```
# Transformer model training and evaluation code as defined in the notebook
```
## Step 4: Generate Investment Suggestions
After training the models, use the predictions to generate investment suggestions based on price fluctuations (e.g., long or short positions based on predicted price trends).

# Expected Outputs
The expected outputs include:
* Loss curve: The loss reduction over epochs while training the diffusion and transformer models.
* Predicted prices: The future Bitcoin prices predicted by the transformer model.
* Investment advice: A suggestion to invest in long or short positions based on the predicted trends and a fluctuation control of 10%.
* MAE MSE: Both of them are lower than 0.1.
## Example Outputs:
* Predicted price trends for the next few days or weeks.
* Investment suggestion based on predicted volatility.
* Visualizations of the Bitcoin price trends and model performance.

# Contributor
Peilin Wu - Project Lead, Data Collection, Model Implementation

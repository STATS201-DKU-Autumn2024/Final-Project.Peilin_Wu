# GoogleTrends
When analyzing the search trends for Bitcoin, Dogecoin, and Ethereum, incorporating sentiment analysis can provide deeper insights. Sentiment analysis is a natural language processing (NLP) technique used to identify and extract sentiments or emotions from text. Here's how you can integrate sentiment analysis with Google Trends' MultiTimeline and GeoMap:

## Applications of Sentiment Analysis

### 1. Combining Search Trends with Sentiment Analysis:
* Trends and Sentiment Shifts: By analyzing social media posts, news articles, and forum discussions related to Bitcoin, Dogecoin, and Ethereum, you can understand how public sentiment changes over time. For example, when the search interest for a cryptocurrency rises, sentiment analysis can help determine whether the interest is due to positive market sentiment (like price increases) or negative sentiment (such as market panic).
* Relationship Between Sentiment and Price: By correlating sentiment analysis results with price movements, you can gain insights into how market sentiment affects cryptocurrency prices. Positive sentiment might indicate a price increase, whereas negative sentiment could lead to price declines.
Utilizing Sentiment Analysis Tools:
You can use sentiment analysis tools (such as VADER, TextBlob, or other NLP libraries) to analyze text data related to Bitcoin, Dogecoin, and Ethereum. These tools can help quantify sentiment, generate sentiment scores, and further compare them with Google Trends data.
Integrating MultiTimeline and GeoMap

### 2. Utilizing MultiTimeline:
* In the MultiTimeline visualization, you can display the search trends for Bitcoin, Dogecoin, and Ethereum simultaneously, overlaid with sentiment analysis results. For instance, you could add sentiment scores to the chart to observe the relationship between sentiment fluctuations and search interest. This can help you identify which events or news reports significantly impacted public sentiment.
GeoMap:
* The GeoMap visualization allows you to illustrate the search interest for Bitcoin, Dogecoin, and Ethereum across different regions while combining sentiment analysis results for those regions. For example, you can highlight areas that express positive or negative sentiment towards a specific cryptocurrency. This geographic perspective can reveal differences in market sentiment across regions and help identify potential market opportunities or risks.

By integrating Google Trends' MultiTimeline and GeoMap with sentiment analysis, you can achieve a comprehensive understanding of Bitcoin, Dogecoin, and Ethereum. This analysis approach not only helps you discern the relationship between search trends and market sentiment but also uncovers regional variations in interest and sentiment. Such a multi-dimensional analysis can provide richer information for decision-making, helping you better navigate the dynamics of the cryptocurrency market.

# Cryptocurrency dataset from CryptoCompare
The dataset from CryptoCompare that includes three years of data for Bitcoin, Ethereum, and Dogecoin typically contains several key columns that provide important information about the historical performance of these cryptocurrencies. Here’s a description of what each column represents:

## Dataset Overview

* timeDate:
This column represents the timestamp for each data entry, indicating the date and time at which the data was recorded. It is usually formatted as a Unix timestamp or in a readable date format, allowing you to track the performance of the cryptocurrencies over time.
* close:
The closing price of the cryptocurrency at the end of the specified time period (e.g., daily, hourly). This value is crucial for analyzing price trends and calculating returns over time.
* high:
The highest price reached by the cryptocurrency during the specified time period. This value is important for understanding market volatility and can indicate potential resistance levels.
* low:
The lowest price recorded for the cryptocurrency during the specified time period. This value helps in assessing market support levels and overall price fluctuations.
* open:
The opening price of the cryptocurrency at the beginning of the specified time period. This value is often used in conjunction with the closing price to analyze price movements within the period.
* volume:
The total trading volume of the cryptocurrency during the specified time period. This metric indicates the level of trading activity and liquidity in the market, which can be an important factor in price movements.

# Preprocessing and harmonization steps
## 1. Loading the Data
### Bitcoin Price Data:
* Load the data from the source (e.g., CSV, API) and ensure the date is properly converted.
* Convert time: Convert timestamps to human-readable date formats to facilitate time-series analysis.
* Set index: Set the date column as the index for time-series forecasting.
```
import pandas as pd

# Load Bitcoin price data
price_data_url = 'https://raw.githubusercontent.com/STATS201-DKU-Autumn2024/Problem_Set_1.Peilin_Wu/refs/heads/main/Data/bitcoin0.csv'
price_df = pd.read_csv(price_data_url)

# Convert timestamps to datetime format
price_df['time'] = pd.to_datetime(price_df['time'], unit='ms')
price_df.set_index('time', inplace=True)

# Select relevant columns (close, high, low, open, volume)
price_df = price_df[['close', 'high', 'low', 'open', 'volumefrom', 'volumeto']]
```
## 2. Handling Missing Data
### Check for missing values:\
Missing values in the dataset can negatively affect model performance, especially for time-series forecasting.\
### Impute or drop missing values:\
For time-series data like Bitcoin prices, interpolation (forward fill, backward fill, linear interpolation) is often used to handle missing values.\
For other datasets (like sentiment data), either impute values or remove rows/columns with too many missing values.\
```
# Check for missing values in the Bitcoin price dataset
price_df.isnull().sum()

# Forward fill missing data (interpolation) or drop rows/columns
price_df.fillna(method='ffill', inplace=True)  # Forward fill
```
If sentiment data is present
```
sentiment_df.isnull().sum()
sentiment_df.fillna(method='ffill', inplace=True)  # Forward fill sentiment data
```
## 3. Normalization and Scaling
### Scale numerical data: 
For time-series prediction, it is common to normalize the data, especially when using deep learning models like LSTM. Using MinMaxScaler from sklearn ensures the data is within a fixed range (0, 1) and helps the model train more efficiently.
```
from sklearn.preprocessing import MinMaxScaler

# Normalize the Bitcoin price data (scaling the 'close' column)
scaler = MinMaxScaler(feature_range=(0, 1))
price_df[['close', 'high', 'low', 'open', 'volumefrom', 'volumeto']] = scaler.fit_transform(price_df[['close', 'high', 'low', 'open', 'volumefrom', 'volumeto']])

```
If sentiment data is available and needs scaling:
```
sentiment_scaler = MinMaxScaler(feature_range=(0, 1))
sentiment_df[['sentiment_score']] = sentiment_scaler.fit_transform(sentiment_df[['sentiment_score']])
```
## 4. Feature Engineering
### Create additional time-based features:
For time-series forecasting, additional features like moving averages, percentage change, or rolling windows can help the model capture trends more effectively.
```
# Adding a rolling mean (e.g., 7-day moving average) to the Bitcoin prices
price_df['rolling_mean'] = price_df['close'].rolling(window=7).mean()

# Calculate daily percentage change (returns)
price_df['pct_change'] = price_df['close'].pct_change()
```
### Sentiment data preprocessing:
If sentiment data is available, you may want to preprocess it by calculating weekly or monthly aggregated sentiment scores.
You might also want to apply NLP techniques to analyze the sentiment text, such as sentiment polarity or word embeddings (though in this case, we assume you are using raw aggregated scores like Google Trends data).
## 5. Data Harmonization
### Align timestamps: 
When combining datasets (e.g., Bitcoin prices and sentiment data), it's important to ensure that both datasets have matching timestamps. If the sentiment data is aggregated at a different frequency (e.g., daily, weekly), you'll need to align it with the Bitcoin price data.
```
# Assuming sentiment_df has a 'time' column
sentiment_df['time'] = pd.to_datetime(sentiment_df['time'])
sentiment_df.set_index('time', inplace=True)

# Resampling sentiment data to match the Bitcoin price data frequency (e.g., daily)
sentiment_df_resampled = sentiment_df.resample('D').mean()  # Resample to daily data

```
### Join the datasets: Merge the Bitcoin price data and sentiment data on the timestamp column.

## 6. Train-Test Split
### Time-series data splitting: 
Split the data into training and testing sets, ensuring that the test set represents the future (i.e., the data is split chronologically).
```
# Train-test split: 80% train, 20% test
train_size = int(len(combined_df) * 0.8)
train_data = combined_df[:train_size]
test_data = combined_df[train_size:]

```


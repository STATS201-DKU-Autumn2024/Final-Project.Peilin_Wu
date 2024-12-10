# Visualization Directory for Cryptocurrency Prediction Project

This directory contains visualizations generated as part of the cryptocurrency prediction project. These visualizations provide insights into model performance, data trends, and portfolio management strategies, aiding in the interpretation of results and the effectiveness of the implemented models.

## Contents

### 1. **Portfolio Value Over Time**
   - **File:** `Portfolio_Value.png`
   - **Description:** This visualization shows the value of the cryptocurrency portfolio (Bitcoin and Dogecoin) over time based on model predictions.
   - **Insights:**
     - Tracks portfolio growth or decline based on Bitcoin and Dogecoin price predictions.
     - Demonstrates how the portfolio performs in response to market fluctuations.
   
### 2. **Bitcoin Close: Original, Noisy, and Denoised Data**
   - **File:** `Bitcoin_Close.png`
   - **Description:** This plot compares the original, noisy, and denoised data for Bitcoin’s closing price.
   - **Insights:**
     - Highlights how noise is introduced and then mitigated using the diffusion and denoising processes.
     - Provides a visual comparison to understand the data preprocessing steps.

### 3. **Dogecoin Close: Original, Noisy, and Denoised Data**
   - **File:** `Dogecoin_Close.png`
   - **Description:** This plot compares the original, noisy, and denoised data for Dogecoin’s closing price.
   - **Insights:**
     - Visualizes the effect of adding noise and applying denoising techniques to Dogecoin data.
   
### 4. **Contribution of Bitcoin and Dogecoin to Portfolio Value**
   - **File:** `BTC_Doge_Contribution.png`
   - **Description:** This visualization shows the individual contributions of Bitcoin and Dogecoin to the overall portfolio value over time.
   - **Insights:**
     - Illustrates the performance of each cryptocurrency in the portfolio.
     - Helps to understand how each asset influences the portfolio's total value.

## Purpose of Visualizations

The visualizations in this directory are designed to:

- **Track portfolio performance** by visualizing how the value changes over time with Bitcoin and Dogecoin.
- **Understand the effects of noise and denoising** on cryptocurrency data, which is critical for improving model accuracy and reliability.
- **Evaluate contributions** of each asset to the portfolio, which aids in optimizing investment strategies.

## How to Use

### Access the Visualizations:
Open the `.png` files in this directory to view the visualizations. Each file is named to indicate the type of analysis or insight it provides.

### Incorporate into Reports:
Use these visualizations in project reports or presentations to support findings and illustrate key concepts.

### Recreate the Visualizations:
Run the relevant code in the Jupyter notebook to generate these visualizations. For example:

- **Portfolio Value Over Time** and **Contribution of Bitcoin and Dogecoin** can be recreated in the `portfolio_management_analysis.ipynb` notebook.
- **Noisy and Denoised Data for Bitcoin and Dogecoin** are part of the data preprocessing and visualization steps in the `data_preprocessing_and_visualization.ipynb` notebook.

## Relevant Notebooks

- **Cryptocurrency Portfolio Management Notebook:**  
  `portfolio_management_analysis.ipynb`

- **Data Preprocessing and Visualization Notebook:**  
  `data_preprocessing_and_visualization.ipynb`

These visualizations help you understand the performance of the portfolio and the impact of different cryptocurrencies in an investment context. They also provide transparency into the data preparation process and model predictions.

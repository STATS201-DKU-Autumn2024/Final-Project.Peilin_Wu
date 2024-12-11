## Navigation Instructions

### Code for Simulations and Visualizations
All the simulation and visualization code can be found in the `code/` folder. You will find notebooks that explore different aspects of the data and model:

- **Simulations**: `simulation_notebook.ipynb`
- **Visualizations**: `visualization_notebook.ipynb`

### Datasets and Preprocessing Steps
The raw datasets (Bitcoin and Dogecoin historical price and sentiment data) are available in the `data/` folder. Preprocessing steps include data normalization, noise addition for diffusion modeling, and time-series alignment.

### Documentation and Dependencies
Documentation is included within the `docs/` folder for a detailed description of the methodology, model architecture, and results.

To install the necessary dependencies, use the following:


## Code Execution

1. Clone this repository:
```
git clone https://github.com/STATS201-DKU-Autumn2024/Portfolio-Optimization.git
cd Portfolio-Optimization
```
2. Install dependencies:
```
pip install -r requirements.txt
```
3. Run the Jupyter notebooks or Python scripts for analysis:
* For the model training and testing:
```
jupyter notebook model_notebook.ipynb
```
* For visualizations:
```
jupyter notebook visualization_notebook.ipynb
```
Dependencies

* Python 3.x
* PyTorch 1.x (for neural networks)
* Pandas (for data manipulation)
* NumPy (for numerical operations)
* Matplotlib (for plotting)
* Scikit-learn (for preprocessing and evaluation)
Please ensure all libraries are installed as specified in the requirements.txt file.

## Example Usage

After running the code, you can visualize the model's predictions for portfolio management and price movements in the Visualizations section of the project. The model will simulate cryptocurrency portfolio optimization based on the historical data, allowing you to track the portfolio's value and the contribution of each asset.

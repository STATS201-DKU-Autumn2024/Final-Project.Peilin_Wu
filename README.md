# Final_Project.Peilin_Wu
# Portfolio Optimization Using Diffusion Models and Transformer Networks

## Authors
- **Peilin Wu**: Lead Researcher, Project Developer

## Disclaimer
This project was submitted for **STATS201: Machine Learning for Social Science** at **Duke Kunshan University**, instructed by **Prof. Luyao Zhang** in **Autumn 2024**.

## Acknowledgments
- Special thanks to **Prof. Luyao Zhang** for guidance and support throughout the project.
- Thanks to our classmates for their collaborative feedback and constructive discussions.
- We also acknowledge the support from **AIGC tools** and **open-source software**, which facilitated key aspects of our research and development.
- **Data sources**: Historical cryptocurrency price and sentiment data from Bitcoin and Dogecoin.

## Statement of Intellectual and Professional Growth
This project has significantly contributed to my understanding of machine learning in the context of financial applications, particularly in portfolio optimization. Through the development of this model, I have gained hands-on experience with advanced techniques such as diffusion models, transformer networks, and sentiment analysis. This process has not only strengthened my technical skills but also deepened my appreciation for the ethical challenges in financial decision-making. By combining these tools, I have learned how to navigate the complexities of the cryptocurrency market while ensuring fairness and transparency in algorithmic trading.

## Embedded Media
[Demo Poster](https://www.canva.com/design/DAGUkskNM0s/lo3GT8v9tUPkjuYiA3Xueg/edit)

[Watch the Demo Video](https://duke.zoom.us/rec/share/RwNcVhDeQaAQtY1m1aI-8a4Ml3YQvlyD2YR7hhkaY-in8Li3mUac39o18e6zQFMA.BWCQFuQQrsuTY21B?startTime=1733911457000)

## Table of Contents
1. [Project Overview](code/Readme1.md)
2. [Code Execution](code/Readme1.md)
3. [Dependencies](docs/Readme2.md)
4. [Data Preprocessing](code/code_of_the_model.ipynb)
5. [Model and Results](code/code_of_the_model.ipynb)
6. [Contributing](#contributing)
7. [Flow Chart](Flowchart.png)



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

## Contributing

Feel free to contribute by submitting issues or pull requests. If you want to improve the model, explore additional machine learning techniques, or help with documentation, your contributions are welcome.

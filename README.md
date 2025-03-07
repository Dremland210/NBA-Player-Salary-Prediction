# NBA-Player-Salary-Prediction

Predicting NBA player salaries using historical per-game statistics and inflation-adjusted salary data. This project builds machine learning models to forecast salaries and evaluate player value based on performance metrics.

## Overview

This project leverages NBA per-game statistics from the 2018–19, 2019–20, and 2020–21 seasons to predict salary data for the 2021–22 season. By merging performance metrics with corresponding salary data (adjusted for inflation), the analysis aims to determine if players are overvalued or undervalued, showcasing a data-driven approach to sports analytics.

## Data Sources

The project uses two primary datasets:

1. **Per-Game Statistics**  
   - `pergame_stats_2018-2019.csv`  
   - `pergame_stats_2019-2020.csv`  
   - `pergame_stats_2020-2021.csv`  
   - `pergame_stats_2021-2022.csv`  

   These files are sourced from [Basketball-Reference](https://www.basketball-reference.com/).

2. **Salary Data**  
   - `salaries_2018-2019.csv`  
   - `salaries_2019-2020.csv`  
   - `salaries_2020-2021.csv`  
   - `salaries_2021-2022.csv`  

   Salary information is also extracted from Basketball-Reference. Inflation adjustments (using rates from [in2013dollars](https://www.in2013dollars.com/)) are applied, and salaries are scaled down to millions for easier interpretation.

## Methodology

1. **Loading Data:**  
   Reading CSV files for per-game statistics and salary data.

2. **Cleaning Per-Game Data:**  
   Removing rows with missing values and unneeded columns. Grouping by player to handle multiple entries from split seasons.

3. **Cleaning Salary Data:**  
   Retaining only necessary columns (player names and latest salary figures). Cleaning player names, converting salary strings to integers, adjusting for inflation, scaling salary values down to millions, and removing duplicate entries.

4. **Merging Datasets:**  
   Combining the cleaned per-game statistics with the corresponding salary data, keeping only the players who have data in both datasets.

5. **Exploratory Data Analysis (EDA):**  
   Visualizing player performance and salary distributions, and identifying correlations between performance metrics and salary figures.

## Modeling Approaches

The notebook experiments with several regression techniques to predict player salaries:

- **Linear Regression:**  
  Establishes a baseline for capturing linear relationships between performance metrics and salary.

- **Decision Tree Regression:**  
  Captures non-linear interactions between variables.

- **AdaBoost Regressor:**  
  Uses ensemble methods to combine multiple weak learners for improved prediction accuracy.

Model performance is evaluated using metrics such as Mean Absolute Error (MAE) and Mean Squared Error (MSE).

## Usage

1. **Clone the Repository:**

       git clone https://github.com/dremland210/NBA-Player-Salary-Prediction.git
       cd NBA-Player-Salary-Prediction


2. **Open the Notebook:**  
   - In Google Colab: Upload the `NBA_Player_Salary_Prediction.ipynb` file along with the `data/` folder.  
   - Alternatively, run the notebook in Jupyter Notebook locally.

3. **Run the Analysis:**  
   Execute the notebook cells sequentially to go through data loading, cleaning, merging, EDA, and model building.

## Requirements

This project is implemented in Python and uses the following packages:

- Python 3.x
- [pandas](https://pandas.pydata.org/)
- [numpy](https://numpy.org/)
- [scikit-learn](https://scikit-learn.org/)
- [matplotlib](https://matplotlib.org/)

Install dependencies using pip:

       pip install pandas numpy scikit-learn matplotlib

## Future Improvements

- **Advanced Modeling:** Experiment with additional algorithms (e.g., Random Forest, Gradient Boosting) and cross-validation.
- **Feature Engineering:** Incorporate extra features such as player age, team performance, and injury history.
- **Data Enrichment:** Expand the analysis with more seasons or additional datasets.
- **Enhanced Visualization:** Develop more interactive and detailed visualizations.

## Acknowledgments

- **Data Providers:**  
  - [Basketball-Reference](https://www.basketball-reference.com/) for comprehensive NBA statistics and salary data.  
  - [In2013Dollars](https://www.in2013dollars.com/) for inflation rate information.
- **Google Colab:** For providing a platform to run and share the notebook.
- **Open Source Community:** For the robust Python libraries that support this analysis.

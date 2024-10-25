# Big Mart Sales Forecasting

This project aims to predict sales of products at different Big Mart outlets. It utilizes a comprehensive machine learning pipeline, including data preprocessing, exploratory data analysis, model training, hyperparameter tuning, and model evaluation.

## 1. Data and Libraries

The project utilizes the following libraries:

*   **numpy:** For numerical operations.
*   **pandas:** For data manipulation and analysis.
*   **os:** For operating system related functionalities.
*   **datetime:** For date and time operations.
*   **matplotlib & seaborn:** For data visualization.
*   **scikit-learn:** For machine learning models and evaluation metrics.
*   **catboost, lightgbm, xgboost:** For gradient boosting models.
*   **pickle:** For saving and loading models.

The input data is assumed to be a CSV file named `Train.csv` in the `/content/` directory of a Google Colab environment.

## 2. Project Workflow

The project follows these steps:

1.  **Exploratory Data Analysis (EDA):**
    *   Examines unique values in each column.
    *   Checks for duplicates.
    *   Identifies missing values.
    *   Gathers basic data information.

2.  **Data Cleaning:**
    *   Handles missing values in 'Item_Weight' using mean imputation based on 'Item_Identifier'.
    *   Addresses missing values in 'Outlet_Size' using mode imputation based on 'Outlet_Type'.
    *   Replaces zero values in 'Item_Visibility' with the column mean.
    *   Corrects inconsistencies in 'Item_Fat_Content' categories.
    *   Creates a new feature 'New_Item_Type' from 'Item_Identifier'.
    *   Modifies 'Item_Fat_Content' for 'Non-Consumables'.
    *   Creates 'Outlet_Years' feature representing the outlet's age.

3.  **Data Visualization:**
    *   Generates bar plots for various categorical features (e.g., 'Item_Fat_Content', 'Item_Type', 'Outlet_Establishment_Year').
    *   Visualizes the distribution of 'Item_Weight' using a distplot.
    *   Displays a correlation heatmap for numerical features.

4.  **Data Preprocessing:**
    *   Label encodes categorical columns.
    *   Performs one-hot encoding on specified columns.
    *   Splits the data into training and testing sets.

5.  **Model Training and Evaluation:**
    *   Trains various regression models (Linear Regression, Ridge, Lasso, Decision Tree, Random Forest, Extra Trees, LGBM, XGBoost, and CatBoost).
    *   Evaluates models using cross-validation and R2 score.
    *   Visualizes feature importance for tree-based models.

6.  **Hyperparameter Tuning:**
    *   Performs RandomizedSearchCV for Random Forest, LGBM, XGBoost, and CatBoost.
    *   Prints best parameters, best scores, and R2 scores.
    *   Displays distribution plots of residuals.

7.  **Model Selection and Saving:**
    *   Selects the best-performing model (CatBoost Regressor).
    *   Saves the trained model using pickle for later use.

8.  **Model Testing:**
    *   Loads the saved model and evaluates its performance on the full dataset.


## 3. Observations and Insights

- Several features show a strong correlation with sales.
- Tree-based models generally perform better than linear models.
- Hyperparameter tuning improves model accuracy.
- Missing values were imputed using reasonable strategies.
- Some inconsistencies in data required cleaning before modelling.
- Categorical feature engineering added significant value.

## 4. Conclusion

The project successfully created a robust sales forecasting model using various regression techniques, with CatBoost regressor delivering the highest performance. The model is ready for deployment.

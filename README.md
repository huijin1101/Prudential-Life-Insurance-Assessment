# Prudential-Life-Insurance-Assessment

## Overview
This project is based on a Kaggle competition from 2015, where Prudential Life Insurance sought to streamline its risk assessment process. Traditionally, applicants provided extensive information for risk classification, which was labor-intensive and time-consuming. The goal of this competition was to automate this process using predictive modeling, enabling quicker decision-making with reduced manual intervention.
- Dataset: Contains 126 attributes describing 59,381 applicants, including demographic, medical, and insurance-related features.
- Objective: Predict the ordinal "Response" variable (8 levels) for each applicant, representing their risk classification.
- Challenges:
  - A large number of features requiring extensive feature engineering for feature selection.
  - An ordinal 8-class classification task requiring specialized modeling approaches.

## Methodology
![Approach](images/ML_project_metho.png)
## Key Highlights
1. Comprehensive Exploratory Data Analysis (EDA)
- Diagnosed data quality issues, including missing values and skewed distributions.
- Analyzed feature relationships to uncover redundant variables and isolate key features for targeted engineering and transformation.
- Provided actionable insights that guided feature selection and data preparation, directly contributing to improved model performance.
2. Advanced Feature Engineering
- Missing Data Handling:
 - Dropped features with large missing values and low importance.
 - Imputed significant features using constant, median, or mode strategies.
- Numerical Feature Transformations:
 - Dropped features with low importance.
 - Applied Box-Cox transformation with Standardize to reduce skewness.
 - Designed customized binning for highly skewed features.
- Categorical Feature Encoding:
 - Dropped features with low importance.
 - Used target encoding for the remaining features strongly correlated with the target variable.
- Addressed Label Imbalance:
 - Explored multiple techniques, including SMOTE, ADASYN, and Class Weights, to tackle class imbalance.
 - Selected **SMOTE** for its superior performance, significantly enhancing model accuracy and recall for minority classes.
3. Robust Machine Learning Modeling
- Experimented with diverse machine learning algorithms, including:
 - Logistic Regression, Decision Tree, Random Forest
 - XGBoost, LightGBM, and Neural Networks
 - Stacked Models: Combined XGBoost and LightGBM for improved generalization.
- Leveraged advanced hyperparameter tuning methods:
 - RandomizedSearchCV and BayesSearchCV to optimize model performance efficiently.
- Determined XGBoost as the best-performing model, achieving:
  - Accuracy: ~60%
  - F1-Macro: ~52%
  - Significantly surpassed the baseline model (accuracy ~33%).

## Results
### Modeling Performance

| Model                 | Accuracy (No Data Prep) | F1-Macro (No Data Prep) | Accuracy (With Data Prep) | F1-Macro (With Data Prep) |
|-----------------------|--------------------|--------------------|-----------------------|-----------------------|
| XGBoost               | 58.8%             | 51.7%             | 58.6%                | 52.3%                |
| LightGBM              | 58.6%             | 50.8%             | -                    | -                    |
| Stacked Model         | 58.9%             | 51.8%             | -                    | -                    |
| Random Forest         | -                 | -                 | 57%                  | 49.8%                |
| Logistic Regression   | -                 | -                 | 48.1%                | 43.1%                |
| Decision Tree         | -                 | -                 | 47.2%                | 40.9%                |
| Neural Network        | -                 | -                 | 52%                  | 45%                  |



### Best Model: 
XGBoost achieved an accuracy of ~60% and an F1-macro score of ~52%, significantly surpassing the baseline majority-class model (accuracy ~33%).

## Conclusion
This project demonstrates the importance of comprehensive EDA and advanced feature engineering in tackling complex machine learning problems. By addressing data quality issues, leveraging advanced preprocessing techniques, and experimenting with robust models, we significantly improved performance metrics for an ordinal classification task.

These methodologies are not only effective in the insurance domain but also transferable to other industries requiring predictive modeling on structured datasets.



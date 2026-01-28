# Adaptive Differential Privacy for Data Science

This project investigates the impact of differential privacy on structured data analytics and proposes an adaptive privacy-budget allocation strategy to improve model utility under privacy constraints.

## Overview
Differential Privacy (DP) provides formal guarantees against individual data leakage but often degrades model performance when applied uniformly. This project introduces an adaptive DP framework that allocates privacy budgets based on feature importance, improving predictive utility while maintaining the same average privacy budget.

## Dataset
- Adult Census Income Dataset
- Binary classification: income >50K vs ≤50K
- Structured, real-world data with sensitive attributes

## Methodology
1. Exploratory Data Analysis (EDA)
2. Baseline ML models (Logistic Regression, Random Forest)
3. Fixed Differential Privacy using Laplace mechanism
4. Adaptive Differential Privacy using feature importance
5. Privacy–utility trade-off analysis
6. Fairness analysis across demographic groups

## Key Results
- Fixed DP significantly degrades model performance
- Adaptive DP consistently improves accuracy, F1-score, and ROC AUC under the same privacy budget
- Fairness analysis shows DP does not create bias but interacts with existing dataset imbalance

## Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn
- Jupyter Notebook

## Project Structure
Adaptive_DP_Major_Project/
│
├── data/
│ └── census.csv
├── notebooks/
│ └── Adaptive_Differential_Privacy_for_Data_Science.ipynb
├── results/
│ └── performance_comparison.csv
└── README.md


## How to Run
1. Clone the repository
2. Install dependencies
3. Open the notebook in Jupyter
4. Run cells sequentially

## Key Takeaway
Privacy-preserving data science can be both secure and useful when privacy mechanisms are designed with task awareness and feature relevance in mind.

## Author
Shatakshi Sharma

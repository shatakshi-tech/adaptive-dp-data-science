# Adaptive Differential Privacy for Data Science

This project investigates the impact of differential privacy on structured data analytics and proposes an adaptive privacy-budget allocation strategy to improve model utility under privacy constraints.

##Overview

This project investigates the privacy–utility trade-off in machine learning and proposes a feature-importance–based adaptive differential privacy mechanism for structured data.

Traditional differential privacy applies a uniform privacy budget across all features, often degrading model performance significantly. This project introduces an adaptive approach that allocates privacy budgets according to feature importance, reducing noise on highly informative features while maintaining comparable privacy guarantees.

Using the Adult Census Income dataset, the proposed method demonstrates substantially better predictive performance than fixed differential privacy under the same privacy setting.

##Key Results

At high privacy settings (ε = 0.1):

Method	ROC AUC
No Privacy Baseline	~0.831
Fixed Differential Privacy	~0.431
Adaptive Differential Privacy	~0.731
Main Findings
Adaptive DP improved ROC AUC by approximately 42% over Fixed DP.
Adaptive DP degraded only 12% from the no-privacy baseline.
Fixed DP degraded by approximately 38% under the same privacy budget.
Adaptive privacy allocation preserved model utility while maintaining strong privacy constraints.
Problem Statement

Machine learning models often require access to sensitive personal data. Differential Privacy (DP) protects individual information by adding noise to data or model outputs, but excessive noise can severely reduce predictive performance.

##The goal of this project is to answer:

Can privacy budgets be allocated intelligently to preserve model utility without weakening privacy guarantees?

##Methodology
1. Data Preparation

##Dataset:

Adult Census Income Dataset (UCI)

##Target:

Income > 50K vs ≤ 50K

##Features:

Age
Workclass
Education
Occupation
Sex
Hours-per-week

##Preprocessing:

Missing value handling
One-hot encoding
Feature scaling
Train-test split
2. Baseline Models
Logistic Regression
Random Forest

##Evaluation Metrics:

Accuracy
F1 Score
ROC AUC
3. Fixed Differential Privacy

Implemented a fixed privacy-budget mechanism using Laplace noise injection.

##Characteristics:

Same ε applied to every feature
Uniform noise allocation
Significant utility degradation under strong privacy settings
4. Adaptive Differential Privacy (Proposed)

The proposed approach:

Estimates feature importance.
Allocates privacy budgets proportionally to importance.
Injects feature-specific Laplace noise.
Trains models on privacy-preserving data.

Conceptually:

Feature Importance
        ↓
Adaptive ε Allocation
        ↓
Feature-wise Laplace Noise
        ↓
Model Training

Important features receive lower effective noise, while less informative features receive stronger perturbation.

Privacy–Utility Analysis

A multi-ε experiment was conducted:

ε = 0.05
ε = 0.10
ε = 0.20
ε = 0.30
ε = 0.50
ε = 1.00
ε = 2.00

##For each privacy budget:

Fixed DP
Adaptive DP

were compared using:

ROC AUC
Accuracy
F1 Score

The resulting privacy–utility frontier shows that adaptive DP consistently preserves more predictive utility, particularly in low-ε (high privacy) regimes.

Fairness Analysis

The project additionally evaluates demographic fairness across gender groups.

##Metrics:

Accuracy
True Positive Rate (Recall)
False Negative Rate

##Findings:

Dataset bias exists even without privacy constraints.
Adaptive DP does not amplify existing demographic disparities.
Utility improvements are achieved without significant fairness degradation.

##Technologies Used
Python
Pandas
NumPy
Scikit-learn
Matplotlib
Seaborn
Jupyter Notebook

##Project Structure
adaptive-dp-data-science/
│
├── data/
│   └── census.csv
│
├── notebooks/
│   └── Adaptive_DP_Final.ipynb
│
├── results/
│   ├── performance_comparison.csv
│   ├── privacy_utility_summary.csv
│   └── fairness_results.csv
│
└── README.md
Key Takeaway

This project demonstrates that privacy preservation does not necessarily require sacrificing model utility. By allocating privacy budgets according to feature importance, adaptive differential privacy can substantially outperform fixed privacy mechanisms while maintaining comparable privacy guarantees.

## Author
Shatakshi Sharma

# Host-Based Intrusion Detection System (HIDS)

## Overview

This project implements a Machine Learning-based Host-Based Intrusion
Detection System (HIDS) using the ADFA-LD dataset. System call sequences
are transformed into N-gram TF-IDF features, reduced using Truncated
SVD, balanced with SMOTE, and evaluated using multiple machine learning
models under Stratified 5-Fold Cross Validation.

## Features

-   End-to-end HIDS pipeline
-   Exploratory Data Analysis (EDA)
-   N-gram (2--4) TF-IDF feature extraction
-   Truncated SVD dimensionality reduction
-   SMOTE for class imbalance
-   Stratified 5-Fold Cross Validation
-   Comparison of multiple machine learning models
-   Feature importance analysis
-   SHAP-based model explainability
-   Final evaluation on an unseen test set

## Dataset

The project uses the **ADFA-LD (Australian Defence Force Academy Linux
Dataset)**, which contains:

-   Normal system call traces
-   Validation attack traces
-   Full attack traces

Each sample is represented as a sequence of Linux system calls.

## Workflow

1.  Create the master dataset from raw system call traces.
2.  Perform exploratory data analysis.
3.  Split the data using a stratified 80:20 train-test split.
4.  Perform Stratified 5-Fold Cross Validation.
5.  Extract N-gram TF-IDF features.
6.  Select the optimal number of Truncated SVD components.
7.  Apply SMOTE to the training data.
8.  Train and compare multiple classifiers.
9.  Retrain the best-performing model on the complete training set.
10. Evaluate on the unseen test set.
11. Interpret predictions using feature importance and SHAP.

## Models Evaluated

-   Random Forest
-   Support Vector Machine (SVM)
-   XGBoost
-   LightGBM
-   CatBoost
-   Soft Voting Ensemble
-   Stacking Ensemble

## Evaluation Metrics

-   Accuracy
-   Precision
-   Recall
-   F1 Score
-   ROC-AUC
-   Confusion Matrix

The primary model selection criterion is **Recall**, followed by **F1
Score** and **ROC-AUC**, since missing an intrusion is more costly than
generating a false positive.

## Technologies

-   Python
-   Pandas
-   NumPy
-   Scikit-learn
-   Imbalanced-learn
-   XGBoost
-   LightGBM
-   CatBoost
-   SHAP
-   Matplotlib
-   Jupyter Notebook

## Project Structure

``` text
.
├── HIDS_Project.ipynb
├── artifacts/
├── README.md
└── dataset/
```

## Installation

``` bash
git clone https://github.com/your-username/HIDS.git
cd HIDS
pip install -r requirements.txt
```

If a `requirements.txt` file is unavailable, install the required
packages manually:

``` bash
pip install pandas numpy matplotlib scikit-learn imbalanced-learn xgboost lightgbm catboost shap
```

## Running the Project

1.  Download the ADFA-LD dataset.
2.  Place the dataset in the project directory.
3.  Open `HIDS_Project.ipynb`.
4.  Execute the notebook cells sequentially.

## Future Improvements

-   Real-time intrusion detection
-   Deep learning models (LSTM/Transformers)
-   Hyperparameter optimization
-   REST API deployment
-   Live monitoring dashboard

## Author

**Joshita Sood**

M.Sc. Data Science

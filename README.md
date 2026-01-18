# Handling Missing Data in Healthcare Prediction Models

## Project Overview
This project investigates strategies for handling missing values in clinical datasets (NHANES) to predict hypertension. It benchmarks imputation methods against models that handle missingness natively, analyzing the impact of **Missing Not At Random (MNAR)** data.

## Key Methodologies
- **Data Preprocessing**: Feature selection based on missingness thresholds (>50%) and **One-Hot Encoding** that treats `NaN` as an informative category.
- **Imputation Strategies**: Implemented and compared **Univariate Imputation (Median)** vs. **Multivariate Iterative Imputation (MICE)**.
- **Model Benchmarking**: Compared **Logistic Regression** (on imputed data) vs. **Histogram-based Gradient Boosting (HGBC)** (native missing handling).
- **Bias Analysis**: Demonstrated selection bias in **Complete-Case Analysis** by quantifying distribution shifts in hypertension prevalence.

## Tech Stack
- Python 3.x
- Scikit-learn (IterativeImputer, HistGradientBoostingClassifier)
- Pandas & NumPy

## Results
- **MICE** significantly reduced reconstruction error (MSE: 0.47) compared to Median Imputation (MSE: 1.03).
- **HGBC (Native Handling)** achieved the highest predictive performance (AUROC: 0.865), slightly outperforming imputation-based methods.
- **Complete-Case Analysis** was proven biased, as healthy individuals were more likely to have missing data than hypertensive patients.

## How to Run
1. Install dependencies: `pip install -r requirements.txt`
2. Run the notebook: `Hypertension_Prediction_Missing_Data.ipynb`

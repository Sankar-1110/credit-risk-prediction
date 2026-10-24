# Credit Risk Prediction Using Machine Learning

## 📌 Project Overview

This project uses machine learning to predict whether a credit card customer is likely to default on their next payment. It explores customer data, analyzes patterns associated with default, and compares two classification algorithms: Logistic Regression and Random Forest.

The project focuses on evaluating model performance using multiple metrics rather than accuracy alone, particularly because the dataset contains more non-defaulters than defaulters.

## 🎯 Problem Statement

Financial institutions need to identify customers who may fail to make their credit card payments. This project uses historical customer information to predict the likelihood of default and evaluates how effectively machine learning models identify potential defaulters.

## 📊 Dataset

The project uses the **Default of Credit Card Clients** dataset from the UCI Machine Learning Repository.

- **Number of records:** 30,000
- **Target variable:** `default payment next month`
- **Target value 0:** No default
- **Target value 1:** Default
- **Default rate:** Approximately 22.12%

The dataset contains customer demographic information, credit limits, repayment status, bill statements, and previous payment amounts.
## 📚 Dataset Source and License

This project uses the **Default of Credit Card Clients** dataset provided by the UCI Machine Learning Repository.

- **Creator:** I-Cheng Yeh
- **Source:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients)
- **License:** Creative Commons Attribution 4.0 International (CC BY 4.0)
- **DOI:** https://doi.org/10.24432/C55S3H

The dataset was used for educational and machine learning purposes. Any modifications made to the original dataset should be clearly documented.

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## ⚙️ Project Workflow

1. **Data Loading:** Loaded the dataset into a Pandas DataFrame.
2. **Data Cleaning:** Checked for missing values and duplicate records.
3. **Exploratory Data Analysis:** Examined the target distribution and analyzed customer characteristics associated with default.
4. **Preprocessing:** Separated the features and target variable and excluded the customer ID from the model inputs.
5. **Train-Test Split:** Divided the data into training and testing sets using stratified sampling.
6. **Model Training:** Trained Logistic Regression and Random Forest classifiers.
7. **Model Evaluation:** Compared accuracy, precision, recall, F1-score, and ROC-AUC.
8. **Threshold Analysis:** Evaluated different classification thresholds for the Random Forest model.
9. **Visualization:** Examined feature importance, the confusion matrix, and the ROC curve.

## 🤖 Machine Learning Models

### 1. Logistic Regression

Logistic Regression was used as a baseline classification model. It achieved higher accuracy and precision than Random Forest in the reported test results, but its recall was considerably lower.

### 2. Random Forest

Random Forest was used to capture potentially more complex relationships in the customer data. It achieved better recall, F1-score, and ROC-AUC than Logistic Regression in the reported evaluation.

## 📈 Model Performance

The following results were obtained during model evaluation:

| Metric | Logistic Regression | Random Forest |
|---|---:|---:|
| Accuracy | 80.77% | 77.82% |
| Precision | 68.68% | 49.87% |
| Recall | 23.96% | 59.31% |
| F1-score | 35.53% | 54.18% |
| ROC-AUC | 0.7076 | 0.7747 |

### Key Observations

- Logistic Regression achieved higher accuracy and precision.
- Random Forest identified a greater proportion of actual defaulters.
- Random Forest achieved a higher F1-score, indicating a better balance between precision and recall at the evaluated threshold.
- The Random Forest ROC-AUC of 0.7747 indicates acceptable ability to distinguish between defaulters and non-defaulters.

Based on recall, F1-score, and ROC-AUC, Random Forest was selected as the preferred model for this experiment.

## 🔍 Feature Importance

Feature importance analysis was performed to identify which input variables contributed most to the Random Forest predictions.

Repayment-status variables, particularly `PAY_0` and other `PAY_*` features, were among the important predictors. Credit limit (`LIMIT_BAL`) also contributed to the model.

Feature importance indicates predictive contribution within the trained model; it does not establish a causal relationship.

## ⚠️ Limitations

- The dataset represents a particular credit-card customer population and may not generalize to other populations or lending products.
- The dataset contains more non-defaulters than defaulters.
- The model makes prediction errors, including false positives and false negatives.
- The results depend on the selected features, train-test split, model parameters, and classification threshold.
- The models have not been validated for real-world lending decisions.

## 🚀 Future Improvements

- Perform systematic hyperparameter tuning.
- Evaluate additional classification algorithms.
- Investigate class-imbalance handling techniques.
- Calibrate predicted probabilities.
- Select a decision threshold based on the costs of different prediction errors.
- Evaluate model stability across different data splits.
- Investigate model explainability and fairness.

## ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
cd credit-risk-prediction
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Prepare the dataset

Place the dataset in the `data/` directory using the filename expected by the notebook.

If the dataset is not included in the repository, obtain it from the UCI Machine Learning Repository and place it in that directory.

### 5. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `notebooks/credit_risk_analysis.ipynb` and run the cells in order.

## 👨‍💻 Author

Developed as a machine learning project to practice data analysis, classification, model evaluation, and interpretation.

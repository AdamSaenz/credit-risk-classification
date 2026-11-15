# Credit Risk Classification Using Machine Learning

## Project Overview

This project evaluates the use of supervised machine learning to classify lending applications according to credit risk. The objective is to distinguish healthy loans from high-risk loans and assess whether resampling techniques improve the identification of potentially risky borrowers.

The analysis compares two logistic regression models:

1. A baseline logistic regression model trained on the original training data.
2. A logistic regression model trained on data balanced using random oversampling.

The project emphasizes model evaluation, class imbalance, and the operational tradeoff between identifying risky loans and incorrectly flagging healthy loans.

## Business Problem

Financial institutions must evaluate lending risk while balancing potential credit losses against the opportunity cost of rejecting creditworthy borrowers.

An effective classification model should identify high-risk loans without generating excessive false positives. Because high-risk loans represent a relatively small proportion of the dataset, overall accuracy alone may obscure important weaknesses in detecting the minority class.

This analysis therefore emphasizes balanced accuracy, precision, recall, and confusion matrices.

## Dataset

The dataset contains 77,536 lending observations and includes the following variables:

- Loan size
- Interest rate
- Borrower income
- Debt-to-income ratio
- Number of accounts
- Derogatory marks
- Total debt
- Loan status

The target variable is `loan_status`, where:

- `0` represents a healthy loan.
- `1` represents a high-risk loan.

The dataset contains 75,036 healthy loans and 2,500 high-risk loans, creating substantial class imbalance.

## Technologies and Libraries

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Scikit-learn
- Imbalanced-learn

## Methodology

### 1. Data Preparation

The lending dataset is loaded into a Pandas DataFrame. The predictors are separated from the target variable, and the observations are divided into training and testing sets.

### 2. Baseline Logistic Regression

A logistic regression classifier is trained using the original training data.

Predictions are generated on the test set and evaluated using balanced accuracy, a confusion matrix, and a classification report.

### 3. Random Oversampling

To address class imbalance, `RandomOverSampler` is applied exclusively to the training data.

The oversampled training set contains 56,271 observations for each class.

The original test set remains separate from the resampling procedure.

### 4. Resampled Logistic Regression

A second logistic regression classifier is trained on the oversampled training data and evaluated against the original test set.

This approach allows comparison of the baseline and resampled models without directly oversampling the evaluation data.

## Model Results

The following results are based on the saved outputs in the project notebook.

| Evaluation Metric | Baseline Model | Oversampled Model |
|---|---:|---:|
| Balanced accuracy | 95.20% | 99.37% |
| High-risk loan precision | 84.66% | 84.13% |
| High-risk loan recall | 90.95% | 99.35% |
| Correctly identified high-risk loans | 563 | 615 |
| Missed high-risk loans | 56 | 4 |
| Healthy loans incorrectly flagged | 102 | 116 |

### Interpretation

The oversampled model demonstrates substantially higher recall for high-risk loans.

Compared with the baseline model, it identifies 52 additional high-risk loans while producing 14 additional false positives.

This represents a meaningful improvement in detecting potentially risky lending applications, although the higher false-positive count could lead to additional manual reviews or unnecessary lending restrictions.

The appropriate model ultimately depends on the relative business costs of missed high-risk loans and incorrectly flagged healthy loans.

## Repository Structure

```text
credit-risk-classification/
├── README.md
├── .gitignore
└── Credit_Risk/
    ├── credit_risk_classification.ipynb
    └── lending_data.csv
```

## Reproducing the Analysis

1. Clone or download this GitHub repository.
2. Install Python and Jupyter Notebook.
3. Install the required packages:

   ```bash
   pip install pandas numpy scikit-learn imbalanced-learn notebook
   ```

4. Open a terminal in the `Credit_Risk` folder.
5. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

6. Open `credit_risk_classification.ipynb`.
7. Select **Run All Cells** to execute the analysis.

The notebook expects `lending_data.csv` to be located in the same directory.

## Limitations and Considerations

- The dataset is highly imbalanced, making ordinary accuracy an insufficient standalone evaluation metric.
- Random oversampling duplicates minority-class training observations and may increase the risk of overfitting.
- The reported metrics reflect a particular train/test split and should not be interpreted as guaranteed performance on future lending applications.
- Additional cross-validation, calibration, and independent validation would strengthen confidence in model performance.
- False positives and false negatives have different financial and operational consequences.
- Any real-world credit decision system would require appropriate fairness assessments, regulatory compliance, explainability, monitoring, and human oversight.

## Conclusion

This project demonstrates how class imbalance affects supervised classification and how random oversampling can improve the detection of high-risk loans.

The oversampled logistic regression model achieved a balanced accuracy of approximately 99.37%, compared with 95.20% for the baseline model.

More importantly, high-risk loan recall increased from approximately 90.95% to 99.35%, reducing missed high-risk loans from 56 to 4 in the test set.

The analysis illustrates the importance of evaluating machine learning models using metrics aligned with business risk rather than relying exclusively on overall accuracy.

## Author

**Adam A. Saenz**

Data Analytics | Applied Machine Learning | Business Strategy

[GitHub Profile](https://github.com/AdamSaenz)

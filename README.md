# Loan Approval Prediction

A beginner-friendly machine learning project that predicts whether a housing-loan application is approved or rejected from applicant and loan information.

> **Target clarification:** `Loan_Status` means application approval (`Y`) or rejection (`N`). This dataset does not contain later repayment or default outcomes, so this project is a loan approval prediction project, not a loan default prediction project.

## Dataset

The project uses the Dream Housing Finance Loan Prediction dataset from Kaggle. The supplied files contain:

- `train.csv`: 614 applications with `Loan_Status` labels
- `test.csv`: 367 applications without labels

The dataset includes applicant demographics, income, requested loan amount, loan term, credit history, and property area. `Loan_ID` is an identifier and is excluded from model inputs. Check the dataset's current license and terms before redistributing the CSV files publicly.

## Project files

```text
.
├── data/
│       ├── train.csv
│       └── test.csv
├── notebooks/
│   ├── loan_default_prediciton.ipynb       # Google Colab version; prompts you to upload both CSVs
├── requirements.txt
└── README.md
```

The summary PDF currently leaves the model comparison and final accuracy to be completed after running the notebook.

## Run in Google Colab

1. Open [Google Colab](https://colab.research.google.com/).
2. Upload `notebooks/loan_approval_colab.ipynb`.
3. Run the cells from top to bottom.
4. When prompted, upload both CSV files from `data/`.
5. Review the validation metrics and confusion matrix. The test CSV has no labels, so it cannot be used to calculate accuracy.

## Workflow

1. Inspect column types, missing values, duplicates, and target balance.
2. Explore applicant income, loan amount, approval rates, and numeric correlations.
3. Use a stratified 80/20 train-validation split.
4. Impute missing values, one-hot encode categorical fields, and scale numeric fields in a scikit-learn pipeline.
5. Compare Logistic Regression, Decision Tree, and Random Forest using accuracy, precision, recall, F1-score, and a confusion matrix.
6. Record the measured model results and explain the project limitations.


git push -u origin main
```

Replace the remote URL with the HTTPS URL shown on your GitHub repository page. If `origin` is already configured, skip `git remote add origin` and check it with `git remote -v`. Review `git status` before committing, and confirm the dataset license permits publishing the CSV files. If not, leave `data/raw/` out of the Git commit and explain in this README how to download the data.

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
│   └── raw/
│       ├── train.csv
│       └── test.csv
├── notebooks/
│   ├── loan_approval_colab.ipynb       # Google Colab version; prompts you to upload both CSVs
│   └── loan_approval_starter.ipynb     # Local Jupyter version; reads data/raw/
├── output/
│   └── pdf/
│       └── loan_approval_project_summary.pdf
├── requirements.txt
└── README.md
```

The summary PDF currently leaves the model comparison and final accuracy to be completed after running the notebook. Do not report a score until it has been measured from the validation results.

## Run in Google Colab

1. Open [Google Colab](https://colab.research.google.com/).
2. Upload `notebooks/loan_approval_colab.ipynb`.
3. Run the cells from top to bottom.
4. When prompted, upload both CSV files from `data/raw/`.
5. Review the validation metrics and confusion matrix. The test CSV has no labels, so it cannot be used to calculate accuracy.

## Run locally with Jupyter

From the project root, install the dependencies and start Jupyter:

```bash
python -m pip install -r requirements.txt
jupyter notebook
```

Then open `notebooks/loan_approval_starter.ipynb` and run the cells from top to bottom. Keep the `data/` folder alongside the notebook's project root so its relative file paths work.

## Workflow

1. Inspect column types, missing values, duplicates, and target balance.
2. Explore applicant income, loan amount, approval rates, and numeric correlations.
3. Use a stratified 80/20 train-validation split.
4. Impute missing values, one-hot encode categorical fields, and scale numeric fields in a scikit-learn pipeline.
5. Compare Logistic Regression, Decision Tree, and Random Forest using accuracy, precision, recall, F1-score, and a confusion matrix.
6. Record the measured model results and explain the project limitations.

## Push the project to GitHub

Create an empty repository on GitHub first. Do not select the option to add a README if you want to push this existing README as the first commit. Then open PowerShell in this project folder and run:

```powershell
git add .gitignore README.md requirements.txt data/raw/train.csv data/raw/test.csv notebooks/loan_approval_colab.ipynb notebooks/loan_approval_starter.ipynb output/pdf/loan_approval_project_summary.pdf
git status
git commit -m "Add loan approval prediction project"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

Replace the remote URL with the HTTPS URL shown on your GitHub repository page. If `origin` is already configured, skip `git remote add origin` and check it with `git remote -v`. Review `git status` before committing, and confirm the dataset license permits publishing the CSV files. If not, leave `data/raw/` out of the Git commit and explain in this README how to download the data.

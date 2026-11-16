# Heart Disease ML

**A data science study of heart disease classification using the UCI Cleveland dataset.** Explore the data, compare baseline and machine learning models, and follow a reproducible evaluation from training folds to a held-out test set.

[Open the notebook](heart_disease_analysis.ipynb) · [Dataset and attribution](#dataset) · [Methodology](#methodology)

> **Educational research only.** This project has not been clinically validated and must not be used for diagnosis, treatment, or clinical decisions.

## What is inside?

The notebook takes you through the dataset, exploratory visualizations, leakage-aware preprocessing, model comparison, and an evaluation of the selected model. It compares a majority-class baseline, logistic regression, and a random forest using accuracy, precision, recall, F1 and ROC-AUC. Results are generated when the notebook runs rather than asserted in advance.

## Run the notebook

Use Python 3.10 or later, from the repository root:

```bash
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
python -m pip install -r requirements.txt
jupyter notebook heart_disease_analysis.ipynb
```

Run all cells in order. The CSV path is relative to the repository root. Package versions are bounded rather than fully locked, so results and compatibility can vary across environments.

## Methodology

1. Convert the original diagnosis to binary presence or absence and reserve a stratified 20% test set.
2. Explore training data only. Fit missing-value imputation, numeric scaling and categorical one-hot encoding inside each cross-validation fold.
3. Compare models using five-fold stratified cross-validation on training data and select by mean ROC-AUC.
4. Fit the selected model on all training data and report held-out classification metrics, a confusion matrix and ROC curve.

The dataset is small and historical, so estimates from one split are uncertain. External validation, calibration, subgroup evaluation and clinical assessment are needed before any real-world application. The supplied CSV's precise preparation and intermediary source are unknown.

## Dataset

The original submission describes `heart_disease.csv` as the Cleveland subset of the [UCI Heart Disease dataset](https://archive.ics.uci.edu/dataset/45/heart+disease). The provided CSV includes a header and empty fields for missing values; other transformations are unknown.

Janosi, A., Steinbrunn, W., Pfisterer, M., & Detrano, R. (1989). *Heart Disease* [Dataset]. UCI Machine Learning Repository. [doi:10.24432/C52P4X](https://doi.org/10.24432/C52P4X). UCI lists the dataset under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

## Contributors

Originally created by Group A: **Anas Ben Zitun, Marwan Elamami, Sanad Ben Latif, and Abdul Majed Mraied**. The notebook was subsequently rebuilt for clarity and a more reliable evaluation workflow; it does not reproduce the original model comparisons.

No software license was supplied with the project. Code and notebook rights remain with their respective rights holders unless they choose a license. The dataset has separate terms.

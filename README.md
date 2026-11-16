# Heart Disease Analysis — Group A

An educational data science project exploring the Cleveland subset of the UCI Heart Disease dataset. The notebook examines clinical features, performs exploratory analysis and feature selection, and compares five classifiers for binary disease presence.

**Research only.** This project is not clinically validated and must not be used to diagnose patients or make treatment decisions. The notebook's original clinical deployment recommendations are historical conclusions, not evidence of clinical readiness.

## Project contents

- `heartDisease_GroupA.ipynb` — original analysis, with saved outputs and decorative embedded images removed for a clean repository; a limitations notice has been added.
- `heart_disease.csv` — dataset supplied with the project.
- `testcases.py` — original notebook helper checks. These checks inspect pipeline structure and do not establish that the complete analysis avoids leakage.
- `requirements.txt` — direct dependencies needed to open and run the notebook.

## Getting started

Use Python 3.10 or later and run these commands from the repository root:

```sh
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
python -m pip install -r requirements.txt
jupyter notebook heartDisease_GroupA.ipynb
```

Run cells in order. Dependencies are not pinned because the original environment was not supplied; compatibility and exact reproduction of historical results are not guaranteed. The notebook uses relative paths and should be launched from the repository root.

## Approach and limitations

The notebook explores the dataset, imputes missing values, uses correlation, mutual information and chi-square scores for feature selection, and compares logistic regression, random forest, gradient boosting, XGBoost and LightGBM. It reports classification metrics and ROC-AUC.

- Imputation and feature selection occur before the train/test split. This exposes evaluation data to preprocessing and selection and can bias estimates. Cross-validation also operates on data imputed before its folds.
- Models are compared and selected using the test set, so its results are not an independent final assessment. A separate validation strategy and untouched test set are needed.
- The dataset is small and historical, from a restricted population. Generalization, calibration and clinical utility are unverified.
- Some notebook narrative makes clinical claims or recommendations beyond what this analysis can support; treat them as original commentary, not established findings.
- Results and conclusions have not been independently reproduced in this repository.

## Data attribution

The supplied CSV is described by the original notebook as the Cleveland subset of the [UCI Heart Disease dataset](https://archive.ics.uci.edu/dataset/45/heart+disease). Its exact preparation and intermediary source were not documented in the archive. UCI credits Andras Janosi, William Steinbrunn, Matthias Pfisterer and Robert Detrano for the dataset, DOI [10.24432/C52P4X](https://doi.org/10.24432/C52P4X), and lists it under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). The supplied CSV has a header and represents missing entries as empty fields; other transformations are unknown.

## Contributors

Group A, as credited in the original notebook:

- Anas Ben Zitun
- Marwan Elamami
- Sanad Ben Latif
- Abdul Majed Mraied

No software license was included in the supplied archive. All rights to the project code and notebook remain with their respective rights holders unless a license is added by them. Dataset terms are separate.

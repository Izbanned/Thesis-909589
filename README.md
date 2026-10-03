# Combating Financial Fraud: Anomaly Detection in Transactions and Early Detection of Suspicious Activity Using AI

Code and results for the Master's thesis (Data Science, University of Milano-Bicocca, 2026).
Author: Diias Karimov. Supervisor: Prof. Enrico Moretto.

Thesis release: `v1.0-thesis` (the version cited in Section 3.9).

## What this repository contains

Experiments for five research questions and one supplementary experiment on four public datasets. All splits are chronological (or by month), so no future data leaks into training. The main metric is PR-AUC.

| Question | Topic | Notebook | Results |
|---|---|---|---|
| RQ1, RQ3 | Models and imbalance handling (SMOTE, ADASYN, class weighting) on Credit Card | `notebooks/RQ1,3,4.ipynb` | `results/credit_card/` |
| RQ2 | SHAP/LIME explanations and their stability on IEEE-CIS | `notebooks/RQ2.ipynb` | `results/ieee_cis/` |
| RQ4 | Five-rule baseline vs. XGBoost | `notebooks/RQ4_Rule_vs_AI.ipynb` | `results/credit_card/rq4_rule_vs_ai_comparison.csv` |
| RQ5 | Transfer to PaySim and BAF | `notebooks/RQ5.ipynb` | `results/paysim/`, `results/baf/`, `results/rq5_transferability*` |
| Supplementary | Boosting libraries and temporal drift (PSI) on IEEE-CIS | `notebooks/RQ6_Model_Families_and_Drift.ipynb` | `results/ieee_cis_rq6/` |

## Datasets (not included, download separately)

| Dataset | Source | Downloaded |
|---|---|---|
| ULB Credit Card Fraud | Kaggle: `mlg-ulb/creditcardfraud` | <date> |
| IEEE-CIS Fraud Detection | Kaggle competition: `ieee-fraud-detection` | <date> |
| PaySim | Kaggle: `ealaxi/paysim1` | <date> |
| Bank Account Fraud (BAF, Base variant) | Kaggle: `sgpjesus/bank-account-fraud-dataset-neurips-2022` | <date> |

Put the files into `data/raw/` (see `data/README.md`) or change the paths in the first cells of each notebook.

## How to run

1. Open a notebook in Google Colab (the experiments were run there) or locally.
3. Set the data paths in the first cell.
4. Run all cells. Seeds are fixed in the notebooks.

Suggested order: RQ1/RQ3 → RQ4 → RQ2 → RQ5 → supplementary.

## Results

- `results/<dataset>/*.csv` contain the tables reported in Chapter 4 (aggregated and raw per-seed results).
- `results/<dataset>/figures/` contain the figures used in the thesis.
- Trained models (`.joblib`) are not stored here because of size. Running the notebooks recreates them.

## Environment

Python 3, scikit-learn, XGBoost, LightGBM, CatBoost, imbalanced-learn, SHAP, LIME; run in Google Colab
## Citation

If you use this code, please cite the thesis:
Karimov, D. (2026). *Combating Financial Fraud: Anomaly Detection in Transactions and Building Algorithms for Early Detection of Suspicious Activity Using Artificial Intelligence*. Master's thesis, University of Milano-Bicocca.

## License

<MIT or "All rights reserved">

[![DOI](https://zenodo.org/badge/1224538071.svg)](https://doi.org/10.5281/zenodo.20038382)

# Perception, Acceptance, and Preparedness Regarding Artificial Intelligence Among Primary Care Nurses

This repository provides the code, statistical models, and methodological materials necessary to fully reproduce the analyses for the cross-sectional study on AI adoption among primary care nurses.

## Repository Structure

- `Perception_Acceptance_and_Preparedness.ipynb`: The complete analytical pipeline. This notebook executes the structural validation of the dataset, descriptive statistics, psychometric evaluation (EFA, McDonald's Omega), bivariate analysis, multivariable modeling (Firth-penalized logistic regression), and the directed content analysis of open-ended responses.

## Computational Reproducibility

To ensure the exact reproduction of all stochastic procedures (including factor-analysis initialization and penalized regression estimations), a global random seed (`42`) is strictly enforced throughout the code.

- **Environment:** Python 3.10
- **Key Dependencies:** `pandas` (2.2.2), `numpy` (2.0.2), `scikit-learn` (1.5.2), `statsmodels` (0.14.6), `factor_analyzer`, `pingouin`, and `spaCy` (`es_core_news_sm`).

### Installation

To replicate the execution environment, install the required packages. Note that `scikit-learn` is pinned to version 1.5.2 to maintain compatibility with `factor_analyzer`.

```bash
pip install "scikit-learn==1.5.2" "factor_analyzer==0.5.1" pandas numpy scipy statsmodels pingouin openpyxl spacy matplotlib seaborn
python -m spacy download es_core_news_sm

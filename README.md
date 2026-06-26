[![DOI](https://zenodo.org/badge/1224538071.svg)](https://doi.org/10.5281/zenodo.20038382)

# Perception, Acceptance, and Preparedness Regarding Artificial Intelligence Among Primary Care Nurses

This repository contains the data, code, and methodological materials needed to reproduce the analyses reported in the cross-sectional study on artificial intelligence (AI) perception, acceptance, and preparedness among primary care nurses, measured with the SHAIP questionnaire.

## Repository structure

| File | Description |
|------|-------------|
| `SHAIP-Statistical-Analysis.ipynb` | Complete analytical pipeline (see *Methods summary* below). |
| `Data Set.csv` | De-identified survey data (102 respondents × 26 variables) exported from the online questionnaire (original Galician labels). Includes the ten SHAIP Likert items and the two open-ended questions. |
| `Revisor_1.csv` / `Revisor_2.csv` | Independent presence/absence coding of the 101 open-ended barrier responses by two coders, used for the inter-coder reliability analysis. |
| `discrepancies_resolved.xlsx` | Consensus resolution of the coding disagreements between the two coders; source of the final barrier prevalences reported in Table 4. |
| `AI_Nursing_Analysis_Results.xlsx` | Consolidated output workbook (descriptives, factor loadings, reliability, Firth model and diagnostics, consensus barriers, inter-coder kappa). |

## Methods summary

**Quantitative analysis.** Structural validation of the dataset; descriptive statistics with assumption checks (Shapiro–Wilk test for the normality of age); SHAIP item- and construct-level scores with 95% confidence intervals; psychometric evaluation by exploratory factor analysis (two theory-driven factors, principal axis factoring with varimax rotation), with reliability assessed by both Cronbach's alpha and McDonald's omega; bivariate comparisons of users versus non-users (chi-square with Yates' continuity correction, Fisher's exact test where expected counts were below five, and the Mann–Whitney U test for age); and multivariable modelling with Firth-penalized logistic regression. Given the events-per-variable ratio of 5:1, confidence intervals were obtained by profile penalized likelihood and p-values by the penalized likelihood-ratio test rather than Wald approximations, with point estimates cross-checked against standard maximum likelihood. A sensitivity analysis excluding "don't know" responses is reported.

**Qualitative analysis.** The two open-ended questions were analysed with a directed (deductive) content-analysis approach. A predefined dictionary (codebook) operationalised each category, and responses were coded by case-insensitive lexical matching against the category terms. The coding is rule-based and does not involve natural-language-processing models or interpretive thematic analysis. The reliability of the coding scheme was assessed by having two coders independently code all 101 barrier responses; agreement was quantified with Cohen's kappa per category (mean kappa = 0.639, substantial agreement). Disagreements were resolved by consensus, and the consensus coding is the source of the values reported in Table 4.

## Computational reproducibility

A global random seed (`42`) is set so that every stochastic procedure returns identical results on re-execution.

- **Environment:** Python 3.10
- **Key dependencies:** `pandas` (2.2.2), `numpy` (2.0.2), `scipy`, `scikit-learn` (1.5.2), `statsmodels` (0.14.6), `factor_analyzer` (0.5.1), `pingouin`, `openpyxl`, `matplotlib`, `seaborn`.

`scikit-learn` is pinned to 1.5.2 to maintain compatibility with `factor_analyzer`.

### Installation

```bash
pip install "scikit-learn==1.5.2" "factor_analyzer==0.5.1" pandas numpy scipy statsmodels pingouin openpyxl matplotlib seaborn
```

### How to run

Open `SHAIP-Statistical-Analysis.ipynb` in Jupyter or Google Colab and run the cells in order. The notebook will prompt for file uploads at the appropriate steps:

1. `Data Set.csv` — at the data-loading step (Section 2).
2. `Revisor_1.csv` and `Revisor_2.csv` — at the inter-coder reliability step (Section 9.1).
3. `discrepancies_resolved.xlsx` — at the consensus step (Section 9.2).

All tables and diagnostics are consolidated into `AI_Nursing_Analysis_Results.xlsx` in the final cell.

## Citation

If you use these materials, please cite the dataset/code via its DOI:

> Vences Garrido, A. *Perception, acceptance, and preparedness regarding artificial intelligence among primary care nurses: data and analysis code.* Zenodo. https://doi.org/10.5281/zenodo.20038382

## License

Released under the terms of the `LICENSE` file in this repository.

[![DOI](https://zenodo.org/badge/1224538071.svg)](https://doi.org/10.5281/zenodo.20038382)

# Perception, Acceptance, and Preparedness Regarding Artificial Intelligence Among Primary Care Nurses

This repository contains the data, code, and methodological materials needed to reproduce the analyses reported in the cross-sectional study on artificial intelligence (AI) perception, acceptance, and preparedness among primary care nurses, measured with the SHAIP questionnaire.

## Repository structure

| File | Description |
|------|-------------|
| `SHAIP-Statistical-Analysis.ipynb` | Complete analytical pipeline (see *Methods summary* below). |
| `Data Set.csv` | De-identified survey data (102 respondents × 26 variables) exported from the online questionnaire (original Galician labels). Includes the ten SHAIP Likert items and the two open-ended questions. |
| `Revisor 1.csv` / `Revisor 2.csv` | Independent presence/absence coding of the open-ended **barriers** responses by two coders, used for the inter-coder reliability analysis. |
| `discrepancies_resolved.xlsx` | Consensus resolution of the coding disagreements for the barriers qualitative analysis; source of the final prevalences reported in Table 4. |
| `Revisor1.1.xlsx` / `Revisor2.2.xlsx` | Independent presence/absence coding of the open-ended **training areas** responses by two coders. |
| `Areas_discrepancia_resueltas_Final.xlsx` | Consensus resolution of the coding disagreements for the training areas qualitative analysis; source of the final prevalences reported in Table 5. |

*(Note: The final output workbooks containing the consolidated tables, metrics, and models—`AI_Nursing_Analysis_Results.xlsx` and `AI_Nursing_Training_Areas.xlsx`—are generated automatically upon successfully running the notebook and are not tracked in this repository).*

## Methods summary

**Quantitative analysis.** Structural validation of the dataset; descriptive statistics with assumption checks (Shapiro–Wilk test for the normality of age); SHAIP item- and construct-level scores with 95% confidence intervals. Psychometric evaluation was conducted via exploratory factor analysis (two theory-driven factors, principal axis factoring with varimax rotation), with reliability assessed by both Cronbach's alpha and McDonald's omega. Bivariate comparisons of users versus non-users applied chi-square with Yates' continuity correction, Fisher's exact test where expected counts were below five, and the Mann–Whitney U test for age. Multivariable modelling utilized Firth-penalized logistic regression. Given the events-per-variable ratio of 5:1, confidence intervals were obtained by profile penalized likelihood and p-values by the penalized likelihood-ratio test rather than Wald approximations, with point estimates cross-checked against standard maximum likelihood. A sensitivity analysis excluding "don't know" responses is included.

**Qualitative analysis.** The two open-ended questions (perceived barriers and training interests) were analysed using a directed (deductive) content-analysis approach. Predefined dictionaries (codebooks) operationalised each category, and responses were initially coded by case-insensitive lexical matching. The coding is rule-based and does not involve natural-language-processing models or interpretive thematic analysis. To assess the reliability of the coding scheme, two coders independently coded all responses for both questions. Agreement was quantified with Cohen's kappa per category, yielding substantial agreement for both the barriers analysis (mean kappa = 0.639) and the training areas analysis (mean kappa = 0.680). All disagreements were subsequently resolved by human consensus, which serves as the definitive source for the reported prevalences.

## Computational reproducibility

A global random seed (`42`) is set so that every stochastic procedure (factor-analysis initialisation, penalised regression, resampling) returns identical results on re-execution.

- **Environment:** Python 3.10
- **Key dependencies:** `pandas` (2.2.2), `numpy` (2.0.2), `scipy`, `scikit-learn` (1.5.2), `statsmodels` (0.14.6), `factor_analyzer` (0.5.1), `pingouin`, `openpyxl`, `matplotlib`, `seaborn`.

`scikit-learn` is explicitly pinned to version 1.5.2 to maintain compatibility with `factor_analyzer`.

### Installation

```bash
pip install --quiet "scikit-learn==1.5.2" "factor_analyzer==0.5.1" pandas numpy scipy statsmodels pingouin openpyxl matplotlib seaborn
```

### How to run

Open `SHAIP-Statistical-Analysis.ipynb` in Jupyter or Google Colab and execute the cells in sequence. The notebook is designed to halt and prompt for file uploads at the specific stages where they are required:

1. `Data Set.csv` — at the data-loading step (Section 2).
2. `Revisor 1.csv` and `Revisor 2.csv` — at the barriers inter-coder reliability step (Section 9.1).
3. `discrepancies_resolved.xlsx` — at the barriers consensus resolution step (Section 9.2).
4. `Revisor1.1.xlsx` and `Revisor2.2.xlsx` — at the training areas inter-coder reliability step (Section 9.2).
5. `Areas_discrepancia_resueltas_Final.xlsx` — at the training areas consensus resolution step (Section 9.2).

All tables and model diagnostics are automatically consolidated and exported to Excel workbooks in the final cells.

## Citation

If you use these materials, please cite the dataset/code via its DOI:

> Vences Garrido, A. *Perception, acceptance, and preparedness regarding artificial intelligence among primary care nurses: data and analysis code.* Zenodo. [https://doi.org/10.5281/zenodo.20038382](https://doi.org/10.5281/zenodo.20038382)

## License

Released under the terms of the `LICENSE` file in this repository.

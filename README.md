# Perception, Acceptance, and Preparedness Regarding Artificial Intelligence Among Primary Care Nurses

This repository contains the analysis code for the cross-sectional study

## Citation
Vences Garrido A, Vicario-Merino Á, Buerba Díaz A. Perception, acceptance, 
and preparedness regarding artificial intelligence among primary care nurses: 
A cross-sectional study. PLOS ONE. 2026; [in press].

## Contents
- `Perception_Acceptance_and_Preparedness...ipynb` — Full Jupyter notebook 
  with all analyses (descriptive, psychometric, bivariate, Firth-penalized 
  logistic regression, NLP).

## Reproducibility
- **Language:** Python 3.10
- **Random seed:** 42
- **Key packages:** pandas 2.2.2, numpy 2.0.2, scipy, statsmodels 0.14.6, 
  scikit-learn, factor_analyzer, pingouin, spaCy (`es_core_news_sm`)

## Installation
```bash
pip install pandas numpy scipy statsmodels scikit-learn factor_analyzer pingouin openpyxl spacy matplotlib seaborn
python -m spacy download es_core_news_sm
```

## Data
The de-identified dataset used in this analysis is available upon request 
from the corresponding author / [or include here if you upload it].

## License
MIT — see LICENSE file.

## Contact
Adrián Vences Garrido — adrian.vences.garrido@sergas.es

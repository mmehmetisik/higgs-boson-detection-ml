# higgs-boson-detection-ml

A comprehensive machine learning solution for detecting Higgs Boson particles using simulated CERN ATLAS detector data from the Kaggle competition.

## 🎯 Competition Overview

The challenge involves classifying particle collision events from CERN's Large Hadron Collider into two categories:
- **Signal**: Events producing Higgs Boson particles
- **Background**: Events without Higgs Boson production

Each event contains 28 physics-based features representing particle trajectories and decay products. The evaluation metric is ROC-AUC.

## 📊 Repository Structure
```
higgs-boson-detection-ml/
├── notebooks/
│   ├── 01_higgs_boson_eda.ipynb
│   └── 02_higgs_boson_model.ipynb
└── README.md
```

## 🔍 Exploratory Data Analysis (EDA)

**Notebook**: `01_higgs_boson_eda.ipynb`

### Key Findings
- **Class Distribution**: Balanced dataset (53.1% signal, 46.9% background)
- **Missing Patterns**: Identified 5 features with >30% zero values (f8, f12, f16, f20)
- **Feature Correlations**: Strong correlations found between f25, f27, f24 and target
- **Outlier Detection**: 12 features contain outliers requiring treatment

### Visualizations
The analysis includes correlation matrices, distribution plots, and pairwise feature relationships revealing distinct clustering patterns between signal and background events.

## 🚀 Modeling Approach

**Notebook**: `02_higgs_boson_model.ipynb`

### Feature Engineering (9 Layers)
1. **Binary Interactions**: Multiplicative features for top correlated pairs
2. **Polynomial Features**: Squared transformations for non-linear patterns
3. **Triple Interactions**: Three-way feature combinations
4. **Advanced Transformations**: Log and square root transforms
5. **Ratio Features**: Division-based features for relative measurements
6. **Aggregations**: Statistical summaries (mean, std, range)
7. **Binary Combinations**: Logical operations on zero-value indicators
8. **Zero Count Groups**: Total missing value counts
9. **Cross-domain Interactions**: Binary indicators × continuous features

### Model Performance
- **Algorithm**: CatBoost with optimized hyperparameters
- **Cross-Validation**: 5-fold stratified CV
- **Final Score**: 0.804 AUC (±0.002)
- **Feature Count**: 563 engineered features from original 28

### Key Features
Top 5 most important features identified:
1. f25 (13.5% importance)
2. f27 (9.3% importance)
3. f26 (6.5% importance)
4. f24 (6.5% importance)
5. f0 (5.4% importance)

## 🛠️ Technical Stack
- **Python 3.x**
- **Libraries**: pandas, numpy, scikit-learn, catboost, matplotlib, seaborn
- **Platform**: Kaggle Notebooks

## 📈 Results Summary

The solution achieves consistent performance with physics-informed feature engineering being the key differentiator. The comprehensive EDA guided the feature engineering strategy, resulting in a robust model that effectively distinguishes Higgs Boson signals from background noise.

## 🔗 Links
- [Kaggle Competition](https://www.kaggle.com/competitions/higgs-boson-detection-2025)
- [EDA Notebook on Kaggle](https://www.kaggle.com/code/mehmetisik/higgs-boson-detection-eda-2025)
- [Model Notebook on Kaggle](https://www.kaggle.com/code/mehmetisik/higgs-boson-2025-9-layer-feature-eng-catboost)

## 📝 License
MIT

---
*Developed for the Higgs Boson Detection 2025 competition*

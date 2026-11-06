---
name: ml-python-stats-linearalgebra
description: "Data-science engineering skill (ML + Python + Statistics + Linear Algebra): model selection, bias-variance, evaluation, NumPy/Pandas/scikit-learn patterns, hypothesis tests, regression, PCA/SVD. Use for ML pipelines, Python data code, statistical testing and linear algebra operations. Triggers: machine learning, ML, model, scikit-learn, pandas, numpy, statistics, hypothesis test, regression, PCA, SVD, eigen, python data."
---

# ML, Python, Statistics & Linear Algebra

## Core Philosophy
This skill is not a textbook; it is a **decision aid for practitioners**. The agent already knows basic concepts; the value is in **model selection, evaluation discipline, idiomatic code patterns and avoiding the failure modes** (leakage, wrong metric, p-hacking) that textbooks mention but don't operationalize.

## Core Formula
> **Engineering Value = (right model chosen) + (right metric) + (no leakage) + (idiomatic code) + (correct test)**
A pipeline with leakage or the wrong metric is worse than no pipeline.

## Thinking Patterns (Mindset)
- **Before choosing a model, ask: "What is the simplest model that could work and what's the baseline?"** Start simple; add complexity only if justified.
- **Before evaluating, ask: "Is there data leakage between train and test?"** Leakage invalidates everything.
- **Before reporting a metric, ask: "Does this metric match the business problem?"** Accuracy on imbalanced data is misleading.
- **Before running a test, ask: "What are the assumptions and are they met?"** Wrong test = wrong conclusion.
- **Before inverting a matrix, ask: "Is SVD more stable here?"** Numerical stability matters.

## Decision Tree
```
What is the task?
├── Classification - logistic regression/RF/XGBoost; metric: F1/AUC (imbalanced) or accuracy (balanced)
├── Regression - linear/ridge/lasso; metric: RMSE/MAE/R²
├── Clustering - K-means/DBSCAN/hierarchical; metric: silhouette
├── Dimensionality - PCA/t-SNE/UMAP
└── Time series - ARIMA/Prophet/LSTM (need temporal CV)

Is the data tabular?
├── Yes - gradient boosting (XGBoost/LightGBM) usually wins
└── No - (images/text) - deep learning

Is there leakage risk?
├── Yes - fix pipeline (fit on train only, transform test)
└── No - proceed
```

## Procedures (Domain-Specific)
1. Step 1: Define the task (classification/regression/clustering/etc) and the metric.
2. Step 2: Check for data leakage between train and test.
3. Step 3: Select the simplest model that could work; establish a baseline.
4. Step 4: Train with cross-validation; tune hyperparameters.
5. Step 5: Evaluate on held-out test with the right metric.
6. Step 6: Check assumptions (for stats) and numerical stability (for LA).
Workflow: task -> leakage check -> baseline -> train/CV -> evaluate -> assumptions.

## Core Mental Models

### Machine Learning
1. **Bias-variance tradeoff.** Underfitting (high bias) vs. overfitting (high variance). Regularization, CV, ensembles balance them.
2. **Supervised vs. unsupervised.** Labeled (classification/regression) vs. unlabeled (clustering/dimensionality reduction).
3. **Feature engineering.** Good features > fancy models. Scaling, encoding, selection matter.
4. **Evaluation.** Train/val/test split; metrics: accuracy, precision/recall/F1, AUC, RMSE, MAE. Match metric to problem.
5. **Ensembles.** Bagging (RF), boosting (XGBoost/LightGBM), stacking. Often beat single models.
6. **Deep learning.** Neural nets for complex patterns; needs data, compute, regularization.

### Python
7. **Pythonic code.** Comprehensions, generators, context managers, decorators, type hints.
8. **Data stack.** NumPy (arrays), Pandas (DataFrames), scikit-learn (ML), matplotlib/seaborn (viz).
9. **Performance.** Vectorize; avoid Python loops; profile before optimizing.

### Statistics
10. **Inference.** Hypothesis tests, p-values, CIs, effect sizes. Don't confuse significance with importance.
11. **Regression.** Linear/logistic, assumptions (linearity, independence, homoscedasticity, normality), diagnostics.
12. **Bayesian vs. frequentist.** Priors + likelihood vs. long-run frequency.

### Linear Algebra
13. **Vectors/matrices.** Dot products, multiplication, transpose, inverse. Foundation of ML.
14. **Eigenvalues/eigenvectors.** PCA, spectral methods, stability.
15. **SVD.** Dimensionality reduction, recommender systems, pseudo-inverse.
16. **Norms & distances.** L1, L2, cosine similarity.

## MANDATORY Triggers
- **MANDATORY - READ** `chapters/ch01-ml-fundamentals.md` when selecting/evaluating a model.
- **MANDATORY - READ** `chapters/ch03-statistics.md` when running hypothesis tests or regression.
- **MANDATORY - READ** `chapters/ch04-linear-algebra.md` when doing PCA/SVD/matrix ops.
- **Do NOT load** all chapters for a simple term lookup; use glossary only.

## Edge Cases & Failure Modes
- **Data leakage:** fit on train only; transform test with train-fitted transformers; never peek at test.
- **Imbalanced data:** accuracy is misleading; use F1/AUC/PR curves; consider resampling or class weights.
- **Small sample:** high variance; prefer simpler models, more CV folds, Bayesian methods.
- **Non-stationary data:** time-series needs temporal CV; random split leaks future info.
- **Multicollinearity:** high VIF; use Ridge or drop redundant features.
- **Numerical instability:** avoid direct inverse; use SVD or solve.

## Anti-Patterns (NEVER)
- **NEVER leak test data into training** because fit transformers on train only; leakage invalidates all metrics and gives false confidence.
- **NEVER use accuracy on imbalanced data** because it's misleading; use F1, AUC or PR-AUC; a 99% majority class gives 99% accuracy by guessing.
- **NEVER p-hack** because don't run 20 tests and report the one that passed; correct for multiple comparisons (Bonferroni/FDR).
- **NEVER confuse significance with importance** because a tiny effect can be significant with large n; report effect size + CI.
- **NEVER loop over large arrays in Python** because vectorize with NumPy/Pandas; loops are 10-100x slower.
- **NEVER invert a matrix directly when SVD is available** because direct inverse is numerically unstable; use `np.linalg.solve` or SVD.
- **NEVER skip assumption checks** because wrong test = wrong conclusion; verify normality, homoscedasticity, independence before choosing.

## Output Format
```
ML/STATS DIAGNOSIS
Task: <classification/regression/clustering/etc>
Data: <tabular/non-tabular, size, imbalance>
Model recommended: <name + why>
Metric: <name + why>
Validation: <CV strategy, leakage check>
Risks: <leakage/imbalance/small-n/etc.>
Next step: <concrete action>
```

## Voice Calibration
Technical, precise, code-oriented. Favors concrete examples and runnable snippets. No hand-waving.
---

See `glossary.md`, `patterns.md`, `cheatsheet.md`, `chapters/`.

# Chapter 1: ML Fundamentals

## Key concepts

- **Bias-variance tradeoff:** underfit (high bias) vs overfit (high variance).
- **Algorithms:** linear/logistic regression, decision trees, RF, SVM, KNN, naive Bayes, XGBoost, neural nets.
- **Evaluation:** train/val/test; accuracy, precision/recall/F1, AUC, RMSE.
- **Cross-validation:** k-fold; avoid data leakage.
- **Regularization:** L1 (Lasso), L2 (Ridge), elastic net.
- **Ensembles:** bagging, boosting, stacking.

## Operational heuristics

- Start simple (linear/logistic); add complexity only if needed.
- Always hold out a test set; use cross-validation.
- Match metric to problem (imbalanced → F1/AUC, not accuracy).
- Feature engineering often beats model choice.

## Application prompt

"Which model fits this data/problem? What metric? How to validate?"

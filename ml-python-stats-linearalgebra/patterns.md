# Patterns — ML/Python/Stats/LA

## Techniques
1. **ML pipeline:** load → EDA → feature eng → split → train → evaluate → tune.
2. **Cross-validation:** k-fold; avoid leakage.
3. **Regularization:** L1/L2; tune alpha.
4. **Ensemble:** RF/XGBoost for tabular.
5. **Vectorization:** NumPy/Pandas over loops.
6. **Pipelines:** sklearn Pipeline to prevent leakage.
7. **Test selection:** match test to data type/assumptions.
8. **Effect size + CI:** beyond p-values.
9. **PCA/SVD:** dimensionality reduction.
10. **Cosine similarity:** for embeddings/text.

## Anti-patterns
- Data leakage.
- Wrong metric for imbalanced data.
- Python loops over large arrays.
- p-hacking.
- Confusing correlation/causation.
- Direct matrix inverse (use SVD).

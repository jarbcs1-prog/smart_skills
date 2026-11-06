# Chapter 4: Linear Algebra

## Key concepts

- **Vectors:** dot product, norm, cosine similarity.
- **Matrices:** multiplication, transpose, inverse, determinant, rank.
- **Eigen:** eigenvalues/eigenvectors; PCA, spectral methods.
- **SVD:** singular value decomposition; dimensionality reduction, pseudo-inverse.
- **Norms:** L1, L2, Frobenius; regularization.
- **Applications:** linear regression (normal equations), PCA, recommender systems.

## Operational heuristics

- Prefer SVD-based solutions (numerically stable) over direct inverse.
- PCA: center data, compute covariance, eigendecompose.
- Cosine similarity for text/embeddings; Euclidean for dense numeric.

## Application prompt

"What linear algebra operation is needed? Is SVD more stable than inverse?"

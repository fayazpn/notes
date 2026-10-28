# Unsupervised Learning Basics

Map: [[Maps/Machine learning|Machine learning]]

## Summary

Finding structure in data without labeled outputs - clustering, dimensionality reduction, and anomaly detection.

## Key points

- K-means clustering groups points by similarity; choosing K is itself a modeling decision (elbow method, silhouette score)
- PCA (Principal Component Analysis) reduces dimensionality while preserving as much variance as possible
- No ground truth means evaluation is harder - relies on domain judgment and internal metrics, not accuracy
- Common uses: customer segmentation, anomaly detection, visualization of high-dimensional data

## Practice

- [ ] Run K-means on a dataset and use the elbow method to pick K
- [ ] Apply PCA to reduce a dataset to 2 dimensions and visualize the clusters
- [ ] Explain in one sentence why unsupervised learning is harder to evaluate than supervised learning

## Related

- [[Notes/Machine learning/Supervised Learning Basics|Supervised Learning Basics]]
- [[Notes/Machine learning/NumPy Fundamentals|NumPy Fundamentals]]

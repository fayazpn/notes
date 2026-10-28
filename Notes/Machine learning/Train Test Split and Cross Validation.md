# Train Test Split and Cross Validation

Map: [[Maps/Machine learning|Machine learning]]

## Summary

Splitting data so a model is evaluated on data it has never seen, giving an honest estimate of real-world performance.

## Key points

- A basic train/test split (e.g. 80/20) is the minimum bar - never evaluate on training data
- K-fold cross-validation trains/evaluates K times on different splits, reducing variance in the performance estimate
- Stratified splitting preserves class proportions - critical for imbalanced data
- Time-series data needs a time-based split, not a random one, to avoid leaking the future into training

## Practice

- [ ] Perform a stratified 80/20 train/test split on an imbalanced dataset
- [ ] Run 5-fold cross-validation on a model and report mean/std of the scores
- [ ] Explain why a random split is wrong for time-series forecasting

## Related

- [[Notes/Machine learning/Feature Engineering|Feature Engineering]]
- [[Notes/Machine learning/Model Evaluation Metrics|Model Evaluation Metrics]]
- [[Notes/Machine learning/Overfitting and Regularization|Overfitting and Regularization]]

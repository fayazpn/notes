# Model Evaluation Metrics

Map: [[Maps/Machine learning|Machine learning]]

## Summary

Choosing the right number to judge model quality - accuracy alone is often misleading, especially with imbalanced data.

## Key points

- Classification: precision, recall, F1, ROC-AUC - accuracy is misleading on imbalanced classes
- Regression: MAE, MSE/RMSE, R² - each penalizes errors differently (RMSE punishes large errors more)
- Confusion matrix shows exactly where a classifier is wrong (false positives vs false negatives)
- Pick the metric that matches the business cost of different error types, not just the most common one

## Practice

- [ ] Compute precision, recall, and F1 for a classifier and interpret the confusion matrix
- [ ] Explain why accuracy is misleading on a 95/5 imbalanced dataset
- [ ] Compare MAE vs RMSE on a regression model's predictions and explain the difference

## Related

- [[Notes/Machine learning/Supervised Learning Basics|Supervised Learning Basics]]
- [[Notes/Machine learning/Handling Imbalanced Data|Handling Imbalanced Data]]
- [[Notes/Machine learning/Train Test Split and Cross Validation|Train Test Split and Cross Validation]]

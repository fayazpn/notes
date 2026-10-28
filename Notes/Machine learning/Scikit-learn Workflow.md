# Scikit-learn Workflow

Map: [[Maps/Machine learning|Machine learning]]

## Summary

The standard Python ML library - a consistent `fit`/`predict`/`transform` API across dozens of algorithms.

## Key points

- Estimators use `.fit(...)`; prediction and transformation methods depend on the estimator type
- `Pipeline` chains preprocessing and modeling steps into one object, preventing leakage between train/test
- `GridSearchCV`/`RandomizedSearchCV` automate hyperparameter search with built-in cross-validation
- `.transform()` vs `.fit_transform()` - fit only on training data, transform (not re-fit) on test data

## Practice

- [ ] Build a scikit-learn `Pipeline` combining a scaler, encoder, and classifier
- [ ] Use `GridSearchCV` to tune a model's hyperparameters
- [ ] Explain why calling `.fit_transform()` on the test set is a bug

## Related

- [[Notes/Machine learning/Supervised Learning Basics|Supervised Learning Basics]]
- [[Notes/Machine learning/Feature Engineering|Feature Engineering]]
- [[Notes/Machine learning/Hyperparameter Tuning|Hyperparameter Tuning]]

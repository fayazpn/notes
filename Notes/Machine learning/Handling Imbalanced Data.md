# Handling Imbalanced Data

Map: [[Maps/Machine learning|Machine learning]]

## Summary

When one class vastly outnumbers another (fraud detection, rare disease), naive models learn to just predict the majority class.

## Key points

- Resampling: oversample the minority class (SMOTE) or undersample the majority class
- Class weights: tell the model to penalize minority-class errors more heavily during training
- Accuracy alone can hide minority-class failures. Choose precision, recall, F1, PR-AUC, or ROC-AUC according to the decision - see [[Notes/Machine learning/Model Evaluation Metrics|Model Evaluation Metrics]]
- Always resample only the training set, never the test set, to keep evaluation realistic

## Practice

- [ ] Apply SMOTE to oversample a minority class and retrain a classifier
- [ ] Compare a model with class weights vs without on an imbalanced dataset
- [ ] Explain why you should never oversample before splitting train/test

## Related

- [[Notes/Machine learning/Model Evaluation Metrics|Model Evaluation Metrics]]
- [[Notes/Machine learning/Supervised Learning Basics|Supervised Learning Basics]]

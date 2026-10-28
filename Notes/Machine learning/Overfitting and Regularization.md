# Overfitting and Regularization

Map: [[Maps/Machine learning|Machine learning]]

## Summary

A model that memorizes training data instead of learning generalizable patterns performs well in training but poorly in the real world.

## Key points

- Signs of overfitting: high training accuracy, much lower validation/test accuracy
- Regularization (L1/Lasso, L2/Ridge) penalizes model complexity to reduce overfitting
- Simpler fixes: more training data, fewer features, early stopping, dropout (for neural nets)
- Underfitting is the opposite failure - the model is too simple to capture real patterns

## Practice

- [ ] Train a model with and without L2 regularization and compare train vs test accuracy
- [ ] Plot a learning curve (training size vs error) to diagnose overfitting vs underfitting
- [ ] Explain early stopping as a regularization technique

## Related

- [[Notes/Machine learning/Train Test Split and Cross Validation|Train Test Split and Cross Validation]]
- [[Notes/Machine learning/Supervised Learning Basics|Supervised Learning Basics]]

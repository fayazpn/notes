# Hyperparameter Tuning

Map: [[Maps/Machine learning|Machine learning]]

## Summary

Systematically searching for the model configuration values (learning rate, tree depth, etc.) that aren't learned from data.

## Key points

- Grid search exhaustively tries every combination; random search samples - often nearly as good, much cheaper
- Bayesian optimization (e.g. Optuna) intelligently narrows the search based on past results
- Tune on validation data or suitable cross-validation splits; reserve the final test set for evaluation - see [[Notes/Machine learning/Train Test Split and Cross Validation|Train Test Split and Cross Validation]]
- Track which hyperparameters were tried and their scores - see [[Notes/Machine learning/Experiment Tracking|Experiment Tracking]]

## Practice

- [ ] Compare grid search vs random search runtime and results on the same model
- [ ] Use Optuna (or similar) to tune 2-3 hyperparameters of a model
- [ ] Explain why hyperparameters must be tuned on a validation set, not the test set

## Related

- [[Notes/Machine learning/Scikit-learn Workflow|Scikit-learn Workflow]]
- [[Notes/Machine learning/Train Test Split and Cross Validation|Train Test Split and Cross Validation]]
- [[Notes/Machine learning/Experiment Tracking|Experiment Tracking]]

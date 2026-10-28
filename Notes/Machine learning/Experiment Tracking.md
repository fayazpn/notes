# Experiment Tracking

Map: [[Maps/Machine learning|Machine learning]]

## Summary

Logging every model training run's parameters, metrics, and artifacts so results are reproducible and comparable.

## Key points

- Tools such as MLflow can record hyperparameters, metrics, and artifacts when logging or supported integrations are configured
- Without tracking, teams lose track of which exact config produced their best model
- Related to [[Notes/Python/Logging|Logging]] but specialized for ML - tracks metrics over epochs, not just text events
- Enables comparing dozens of runs side-by-side to pick the best configuration

## Practice

- [ ] Log a training run's hyperparameters and final metric using MLflow
- [ ] Compare 3 tracked runs with different hyperparameters in an MLflow/W&B dashboard
- [ ] Explain why 'I remember it was around lr=0.01' is not a substitute for experiment tracking

## Related

- [[Notes/Python/Logging|Logging]]
- [[Notes/Machine learning/Hyperparameter Tuning|Hyperparameter Tuning]]

# MLOps and Pipelines

Map: [[Maps/Machine learning|Machine learning]]

## Summary

Applying software engineering discipline (CI/CD, monitoring, versioning) to the ML lifecycle so models stay reliable in production.

## Key points

- Data and model versioning (DVC, model registries) - not just code versioning
- Automated retraining pipelines trigger on a schedule or when new data arrives
- Model monitoring watches for data drift and performance decay after deployment - see [[Notes/Python/Monitoring and Caching|Monitoring and Caching]]
- CI/CD for ML adds data validation and model evaluation gates before deploying a new model version - see [[Notes/Python/CI CD Basics|CI CD Basics]]

## Practice

- [ ] Sketch a pipeline diagram: data ingestion -> validation -> training -> evaluation -> deployment
- [ ] Design a simple drift-detection check comparing new incoming data to training data statistics
- [ ] Explain why a deployed model's performance can silently degrade over time without code changing

## Related

- [[Notes/Python/CI CD Basics|CI CD Basics]]
- [[Notes/Python/Monitoring and Caching|Monitoring and Caching]]
- [[Notes/Machine learning/Experiment Tracking|Experiment Tracking]]
- [[Notes/Machine learning/Model Deployment and Serving|Model Deployment and Serving]]

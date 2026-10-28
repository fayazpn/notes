# Model Deployment and Serving

Map: [[Maps/Machine learning|Machine learning]]

## Summary

Getting a trained model out of a notebook and into a system that can serve real-time or batch predictions.

## Key points

- Wrap a model in an API endpoint (FastAPI/Flask) for real-time inference - see [[Notes/Python/API Design and REST Basics|API Design and REST Basics]]
- Serialize the trained model (`pickle`, `joblib`, or framework-specific formats like ONNX) for loading in production
- Batch inference (scoring a large dataset offline) vs online inference (one request at a time) have very different design needs
- Package the serving app with compatible, pinned runtime dependencies - see [[Notes/Python/Dockerizing Python Apps|Dockerizing Python Apps]]

## Practice

- [ ] Serve a trained scikit-learn model as a FastAPI `/predict` endpoint
- [ ] Containerize that API with Docker so it runs identically anywhere
- [ ] Explain the difference between batch and online inference with an example use case for each

## Related

- [[Notes/Python/API Design and REST Basics|API Design and REST Basics]]
- [[Notes/Python/Dockerizing Python Apps|Dockerizing Python Apps]]
- [[Notes/Python/JSON and Data Serialization|JSON and Data Serialization]]

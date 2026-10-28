# Model gateway project plan

Map: [[Maps/Life and ideas|Life and ideas]]

## Summary

Build a gateway that routes model requests and makes reliability, latency, cost, and output-quality tradeoffs measurable.

## Key points

- Go service for routing, request validation, rate limits, caching policy, timeouts, and fallback behavior.
- Python tools for evaluation datasets, scoring, and model-related experiments.
- Store the request/configuration versions and evaluation results needed to reproduce a comparison, with a deliberate privacy policy.
- Track latency, usage/cost, cache hits, errors, and fallback outcomes.
- Prefer exact or structured evaluation checks when possible. Use subjective grading only with a stated rubric and its limitations.
- Start with one provider and one clear evaluation task; expand only after the baseline works.

## Related

- [[Notes/Life/Learning priorities|Learning priorities]]
- [[Notes/Machine learning/Experiment Tracking|Experiment Tracking]]
- [[Notes/Machine learning/Model Evaluation Metrics|Model Evaluation Metrics]]

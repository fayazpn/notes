# Web performance

Map: [[Maps/Web development|Web development]]

## Summary

Measure loading, responsiveness, and visual stability separately, then use traces to identify the bottleneck.

## Key points

- Core Web Vitals are LCP for largest-content loading, INP for interaction responsiveness, and CLS for unexpected layout shifts. INP replaced FID.
- FCP is another useful loading milestone; it is not the same as the largest content being visible.
- Reserve image and content dimensions to reduce layout shifts.
- Defer non-critical work, reduce long main-thread tasks, and prioritize important resources based on measurement. Lazy-loading the primary visible image can hurt loading performance.
- Script `async` and `defer` have different scheduling rules; neither means “execute only when every other task is finished.”

## Related

- [[Notes/JavaScript/Event loop|Event loop]]
- [[Notes/Web/CSS layout and styling|CSS layout and styling]]

## Sources

- [Web Vitals](https://web.dev/articles/vitals)

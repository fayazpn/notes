# Context cancellation

Map: [[Maps/Go|Go]]

## Summary

A context carries request-scoped deadlines, cancellation signals, and values through a call chain.

## Key points

- Pass the context through operations doing work for that request.
- Cancelling a parent also cancels derived contexts.
- Call the cancellation function returned by `WithCancel`, `WithTimeout`, or `WithDeadline` to release resources.
- Cancellation is cooperative: work must observe it. It does not forcibly kill a goroutine or guarantee that a remote side effect was undone.

## Example

```go
ctx, cancel := context.WithTimeout(parent, time.Second)
defer cancel()
err := doWork(ctx)
```

## Related

- [[Notes/Systems/Concurrency and parallelism|Concurrency and parallelism]]
- [[Notes/Go/HTTP handlers|HTTP handlers]]

## Sources

- [Go context package](https://pkg.go.dev/context)

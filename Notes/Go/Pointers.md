# Pointers

Map: [[Maps/Go|Go]]

## Summary

A pointer holds the address of a value. Go passes pointer values by value, just as it passes other values.

## Key points

- `&value` obtains a pointer; `*pointer` accesses the pointed-to value.
- A function receiving a pointer can modify the shared pointed-to value. Reassigning its local pointer does not reassign the caller's variable.
- The zero pointer is `nil`; dereferencing it panics.
- A pointer does not automatically imply heap allocation. Escape analysis determines placement.
- Choose pointer parameters for mutation, identity, or appropriate copy costs, rather than assuming they are always faster.

## Example

```go
func increment(value *int) {
    *value += 1
}

count := 1
increment(&count)
// count is now 2
```

## Related

- [[Notes/Go/Slices|Slices]]
- [[Notes/Go/Maps|Maps]]

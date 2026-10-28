# Control flow

Map: [[Maps/Go|Go]]

## Summary

`if` selects a branch; `switch` selects among cases. Both can have an initializer scoped to the statement.

## Key points

- Conditions must be boolean expressions; Go does not use truthiness conversions.
- An `if` initializer is useful for an error or value needed only by that branch chain.
- A matching expression-switch case does not fall through automatically.
- An expressionless switch checks boolean cases in order.

## Example

```go
if err := save(); err != nil {
    return err
}

switch status {
case "new", "pending":
    queue()
default:
    ignore()
}
```

## Related

- [[Notes/Go/Scope|Scope]]
- [[Notes/Go/Loops|Loops]]

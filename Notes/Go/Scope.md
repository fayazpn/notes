# Scope

Map: [[Maps/Go|Go]]

## Summary

Go resolves names through lexical scopes, based on where code is declared rather than where a function is called.

## Key points

- Package declarations, function bodies, and nested blocks introduce scopes.
- Inner code can access an enclosing declaration; outer code cannot access an inner local variable.
- A new inner declaration can shadow an outer name, even with a different type.
- Use short scopes for temporary values, such as an `if` initializer, and avoid accidental shadowing.

## Related

- [[Notes/Go/Variables|Variables]]
- [[Notes/Go/Control flow|Control flow]]

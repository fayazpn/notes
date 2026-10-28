# Dictionaries

Map: [[Maps/Python|Python]]

## Summary

Insertion-ordered key-value mappings, backed by a hash table for average O(1) key lookup.

## Key points

- Keys must be hashable. A tuple is hashable only if all its elements are hashable - see [[Notes/Python/Tuples|Tuples]]
- `.get()` avoids KeyError; `defaultdict` avoids manual key-checking
- Dict comprehensions: `{k: v for k, v in items}`
- Merging dicts: `{**d1, **d2}` or the `|` operator (3.9+)

## Example

```python
from collections import defaultdict

counts = defaultdict(int)
counts["BTC"] += 1
missing = counts.get("ETH", 0)  # returns 0; does not insert ETH
```

`items()`, `keys()`, and `values()` return dynamic views. Insertion order does not make a dictionary position-indexed like a list. `pop(key)` removes a selected key; `popitem()` removes the most recently inserted pair.

## Practice

- [ ] Count word frequency in a sentence using a dict
- [ ] Use `collections.defaultdict` to group items by a key
- [ ] Merge two dicts where the second overrides the first

## Related

- [[Notes/Python/Lists|Lists]]
- [[Notes/Python/Sets|Sets]]
- [[Notes/Python/List Comprehensions|List Comprehensions]]

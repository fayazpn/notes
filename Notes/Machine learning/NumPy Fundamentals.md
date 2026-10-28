# NumPy Fundamentals

Map: [[Maps/Machine learning|Machine learning]]

## Summary

The core numerical computing library in Python - fast, vectorized array operations replacing slow Python loops.

## Key points

- `ndarray` is a fixed-type, fixed-shape grid of values - far faster than a Python list for numeric work
- Vectorized operations (`arr * 2`) apply element-wise without an explicit loop
- Broadcasting lets arrays of different shapes combine in arithmetic under specific rules
- Indexing/slicing mirrors lists but adds multi-dimensional slicing: `arr[1:3, :2]`

## Practice

- [ ] Create a 2D array and compute row-wise and column-wise sums
- [ ] Vectorize a loop that squares every element in a list of 1M numbers, and time both versions
- [ ] Explain broadcasting with an example of adding a (3,) array to a (3,3) array

## Related

- [[Notes/Python/Lists|Lists]]
- [[Notes/Python/Performance Profiling|Performance Profiling]]

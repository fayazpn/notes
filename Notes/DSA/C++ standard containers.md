# C++ standard containers

Map: [[Maps/DSA|DSA]]

## Summary

Choose a standard container by its ordering, access, uniqueness, and update requirements.

## Container reference

| Container | Main property |
| --- | --- |
| `std::vector<T>` | Contiguous growable array; random access, amortized constant-time push at the end. |
| `std::deque<T>` | Random access with efficient insertion/removal at either end. |
| `std::list<T>` | Doubly linked list; no random-access indexing. |
| `std::stack<T>` | Last-in, first-out adaptor. |
| `std::queue<T>` | First-in, first-out adaptor. |
| `std::priority_queue<T>` | Highest-priority item at the top; logarithmic push/pop. |
| `std::set<T>` / `std::multiset<T>` | Ordered keys, unique / potentially repeated. |
| `std::map<K,V>` / `std::multimap<K,V>` | Ordered key-value associations, unique / potentially repeated keys. |
| `std::unordered_set` / `std::unordered_map` | Hash-based lookup; average constant-time lookup, no sorted iteration order. |

## Common mistakes

- A vector is not a singly linked list. Elements share one element type.
- `end()` is past the last element; do not dereference it. `back()` returns the last element.
- Inserting into or erasing from a vector can move elements and invalidate iterators. Check the operation's invalidation rules.
- `map[key]` can insert a missing key. Use `find` when inspection must not insert.
- `multiset.erase(value)` removes matching values; erasing one found iterator removes one occurrence.
- `emplace_back` is not universally faster than `push_back`; compare the actual construction and workload.

## Example

```cpp
std::vector<int> values{3, 1, 2};
std::sort(values.begin(), values.end());
for (int value : values) {
    std::cout << value << ' ';
}
```

## Sources

- [Original STL lecture](https://www.youtube.com/watch?v=RRVYpIET_RU)

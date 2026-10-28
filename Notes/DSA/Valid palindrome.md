# Valid palindrome

Map: [[Maps/DSA|DSA]]

## Summary

Use two pointers to compare alphanumeric characters from opposite ends, ignoring case.

## Key points

- Move each pointer past ignored characters before comparing.
- A mismatch ends the scan. Otherwise move both pointers inward.
- The usual exercise uses ASCII input; Python Unicode classification/case rules can require a different specification for general text.
- Time O(n), extra space O(1) for the ASCII problem contract.

## Example

```python
def valid_palindrome(value):
    left, right = 0, len(value) - 1
    while left < right:
        while left < right and not value[left].isalnum():
            left += 1
        while left < right and not value[right].isalnum():
            right -= 1
        if value[left].lower() != value[right].lower():
            return False
        left += 1
        right -= 1
    return True
```

## Related

- [[Notes/DSA/Two Sum in a sorted array|Two Sum in a sorted array]]

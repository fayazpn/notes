# Product except self

Map: [[Maps/DSA|DSA]]

## Summary

For each position, multiply the values before it and after it without using division.

## Key points

- First store the running prefix product before each element.
- Traverse backward and multiply each output by the running suffix product.
- Update a running product after using it so the current value is excluded.
- Time O(n), O(1) auxiliary space excluding the O(n) output. This also handles zeros.

## Example

```python
def product_except_self(nums):
    result, prefix = [], 1
    for value in nums:
        result.append(prefix)
        prefix *= value
    suffix = 1
    for index in range(len(nums) - 1, -1, -1):
        result[index] *= suffix
        suffix *= nums[index]
    return result
```

## Related

- [[Notes/DSA/Two Sum|Two Sum]]

## Sources

- [Original explanation](https://www.youtube.com/watch?v=bNvIQI2wAjk&ab_channel=NeetCode)

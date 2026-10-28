# Encode and decode strings

Map: [[Maps/DSA|DSA]]

## Summary

Length-prefixing makes a list of strings unambiguous even when values contain the delimiter.

## Key points

- Encode each item as decimal length, `#`, then exactly that many characters.
- Decode by reading up to `#`, parsing the length, and consuming that many characters.
- Keep the next cursor at `delimiter_index + 1 + length`. The decoder below assumes data produced by this encoder, not arbitrary untrusted input.
- Time and output space are linear in the encoded size.

## Example

```python
def encode_strings(items):
    return "".join(f"{len(item)}#{item}" for item in items)

def decode_strings(encoded):
    result, index = [], 0
    while index < len(encoded):
        delimiter = encoded.index("#", index)
        length = int(encoded[index:delimiter])
        start = delimiter + 1
        result.append(encoded[start:start + length])
        index = start + length
    return result
```

## Related

- [[Notes/DSA/Valid anagram|Valid anagram]]

## Sources

- [Original explanation](https://www.youtube.com/watch?v=B1k_sxOSgv8&ab_channel=NeetCode)

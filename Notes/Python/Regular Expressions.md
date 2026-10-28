# Regular Expressions

Map: [[Maps/Python|Python]]

## Summary

Pattern-matching language for finding, validating, and extracting text, used via the `re` module.

## Key points

- `re.match` (start only) vs `re.search` (anywhere) vs `re.findall` (all matches)
- Groups `()` capture substrings; named groups `(?P<name>...)` improve readability
- Compile patterns with `re.compile()` when reused for performance
- Greedy `*`/`+` vs lazy `*?`/`+?` quantifiers

## Practice

- [ ] Write a regex to validate a simple email format
- [ ] Extract all numbers from a string using `re.findall`
- [ ] Use named groups to parse a date string into year/month/day

## Related

- [[Notes/Python/Strings|Strings]]

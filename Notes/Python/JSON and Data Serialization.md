# JSON and Data Serialization

Map: [[Maps/Python|Python]]

## Summary

Converting Python objects to/from JSON (and other formats like pickle) for storage or transmission.

## Key points

- `json.dumps`/`json.loads` for strings; `json.dump`/`json.load` for files
- Not all Python objects are JSON-serializable by default (e.g. datetime, custom classes)
- `pickle` serializes arbitrary Python objects but is Python-specific and insecure for untrusted input
- Dataclasses (see [[Notes/Python/Dataclasses|Dataclasses]]) often need a custom encoder to serialize cleanly

## Practice

- [ ] Serialize a dict with a datetime field using a custom JSON encoder
- [ ] Round-trip a nested dict through `json.dumps`/`json.loads`
- [ ] Explain a security risk of unpickling untrusted data

## Related

- [[Notes/Python/Input Output and File Basics|Input Output and File Basics]]
- [[Notes/Python/Dataclasses|Dataclasses]]

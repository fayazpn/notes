# Pandas Fundamentals

Map: [[Maps/Machine learning|Machine learning]]

## Summary

A third-party Python library for labeled tabular data, centered on DataFrames and Series.

## Key points

- `DataFrame` = 2D labeled table; `Series` = 1D labeled column
- `.loc[]` (label-based) vs `.iloc[]` (position-based) indexing
- `.groupby()` splits data into groups, applies a function, and combines results - mirrors [[Notes/Python/Dictionaries|dict-based grouping]]
- Reading data: `pd.read_csv()`, `pd.read_json()`, `pd.read_sql()`

## Practice

- [ ] Load a CSV and compute the mean of a numeric column grouped by a category column
- [ ] Filter rows matching multiple conditions using boolean indexing
- [ ] Explain the difference between `.loc[]` and `.iloc[]` with an example

## Related

- [[Notes/Machine learning/NumPy Fundamentals|NumPy Fundamentals]]
- [[Notes/Python/Dictionaries|Dictionaries]]
- [[Notes/Machine learning/Data Cleaning and Preprocessing|Data Cleaning and Preprocessing]]

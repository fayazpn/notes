# Data Cleaning and Preprocessing

Map: [[Maps/Machine learning|Machine learning]]

## Summary

Handling missing values, duplicates, and inconsistent formats before any analysis or modeling can trust the data.

## Key points

- Missing data strategies: drop (`.dropna()`), impute with mean/median/mode, or a model-based fill
- Detect and remove duplicates with `.duplicated()`/`.drop_duplicates()`
- Type mismatches (numbers stored as strings, inconsistent date formats) are a top source of silent bugs
- Outlier detection (IQR, z-score) before deciding to cap, remove, or keep them

## Practice

- [ ] Impute missing numeric values with the column median and missing categoricals with the mode
- [ ] Detect outliers in a column using the IQR method and decide whether to cap or remove them
- [ ] Standardize inconsistent date strings into a single datetime format

## Related

- [[Notes/Machine learning/Pandas Fundamentals|Pandas Fundamentals]]
- [[Notes/Python/Exception Handling|Exception Handling]]

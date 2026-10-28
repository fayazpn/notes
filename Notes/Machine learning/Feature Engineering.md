# Feature Engineering

Map: [[Maps/Machine learning|Machine learning]]

## Summary

Transforming raw data into inputs (features) that make a model's job easier - often more impactful than the choice of model itself.

## Key points

- Encoding categoricals: one-hot encoding vs label/ordinal encoding, and when each is appropriate
- Scaling: standardization (`z = (x - mean) / std`) vs normalization (min-max) - required for distance-based models
- Feature creation: ratios, date-part extraction (day-of-week, month), interaction terms
- Leakage risk: never fit a scaler/encoder on data that includes the test set

## Practice

- [ ] One-hot encode a categorical column and standardize a numeric column
- [ ] Engineer a new feature (e.g. day-of-week) from a datetime column
- [ ] Explain data leakage with a concrete example involving scaling

## Related

- [[Notes/Machine learning/Data Cleaning and Preprocessing|Data Cleaning and Preprocessing]]
- [[Notes/Machine learning/Train Test Split and Cross Validation|Train Test Split and Cross Validation]]

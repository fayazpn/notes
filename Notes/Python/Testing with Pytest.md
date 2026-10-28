# Testing with Pytest

Map: [[Maps/Python|Python]]

## Summary

Writing automated tests to catch regressions, using the pytest framework, the de facto standard.

## Key points

- Test functions start with `test_`; assertions use plain `assert`
- `@pytest.fixture` provides reusable setup/teardown (e.g. a DB connection)
- `@pytest.mark.parametrize` runs the same test with multiple inputs
- Mocking external calls with `unittest.mock` keeps tests fast and isolated

## Practice

- [ ] Write parametrized tests for a `is_prime()` function covering edge cases
- [ ] Use a fixture to set up and tear down a temporary file for a test
- [ ] Mock an external API call so the test doesn't hit the network

## Related

- [[Notes/Python/Exception Handling|Exception Handling]]
- [[Notes/Python/Code Quality and Linting|Code Quality and Linting]]
- [[Notes/Python/CI CD Basics|CI CD Basics]]

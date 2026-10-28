# Security Best Practices

Map: [[Maps/Python|Python]]

## Summary

Common defensive practices for Python apps handling user input, secrets, and external data.

## Key points

- Never hardcode secrets - use environment variables or a secrets manager, see [[Notes/Python/Config and Environment Variables|Config and Environment Variables]]
- Validate and sanitize all external input (forms, API bodies, file uploads)
- Avoid eval()/exec() on untrusted input, and pickle.loads() on untrusted data
- Keep dependencies updated - known-vulnerable packages are a common attack vector

## Practice

- [ ] Move a hardcoded API key into an environment variable
- [ ] Explain why eval(user_input) is dangerous with a concrete exploit example
- [ ] Add input validation to a function that currently trusts its arguments blindly

## Related

- [[Notes/Python/Database Access and ORMs|Database Access and ORMs]]
- [[Notes/Python/Config and Environment Variables|Config and Environment Variables]]
- [[Notes/Python/Logging|Logging]]

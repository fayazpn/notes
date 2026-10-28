# Logging

Map: [[Maps/Python|Python]]

## Summary

Structured, leveled recording of what a program is doing - replaces scattered print statements in real applications.

## Key points

- Levels: DEBUG < INFO < WARNING < ERROR < CRITICAL - filter by setting a minimum level
- Use a named logger per module: `logging.getLogger(__name__)`
- Handlers route logs to console, files, or external services; formatters control the output shape
- Never log sensitive data (passwords, tokens) - see [[Notes/Python/Security Best Practices|Security Best Practices]]

## Practice

- [ ] Set up a logger that writes INFO+ to console and DEBUG+ to a file
- [ ] Log an exception with full traceback using `logger.exception()`
- [ ] Explain why print() is a poor substitute for logging in production

## Related

- [[Notes/Python/Exception Handling|Exception Handling]]
- [[Notes/Python/Security Best Practices|Security Best Practices]]
- [[Notes/Python/Monitoring and Caching|Monitoring and Caching]]

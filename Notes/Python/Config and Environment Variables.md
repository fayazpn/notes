# Config and Environment Variables

Map: [[Maps/Python|Python]]

## Summary

Keeping configuration (API keys, DB URLs, feature flags) out of code so behavior can change per environment.

## Key points

- `os.environ.get('KEY', default)` reads env vars safely
- `.env` files (loaded via python-dotenv) keep local secrets out of version control - always .gitignore them
- Twelve-Factor App principle: strict separation of config from code
- Typed settings tools can validate environment configuration; Pydantic's settings integration is provided by `pydantic-settings`

## Practice

- [ ] Load a DB URL from a .env file using python-dotenv
- [ ] Add .env to .gitignore and explain why it must never be committed
- [ ] Use Pydantic BaseSettings to type-validate 3 config values

## Related

- [[Notes/Python/Security Best Practices|Security Best Practices]]
- [[Notes/Python/Dockerizing Python Apps|Dockerizing Python Apps]]

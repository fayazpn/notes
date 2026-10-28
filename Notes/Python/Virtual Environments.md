# Virtual Environments

Map: [[Maps/Python|Python]]

## Summary

Isolated Python installations per project so dependencies don't conflict across projects.

## Key points

- `python -m venv .venv` creates one; `source .venv/bin/activate` activates it
- `pip freeze > requirements.txt` snapshots dependencies
- Modern alternative: `poetry` or `uv` manage envs and dependency resolution together
- Never commit `.venv/` to version control

## Practice

- [ ] Create a venv, install a package, and export a requirements.txt
- [ ] Explain why global package installs cause version conflicts across projects
- [ ] Compare venv+pip vs Poetry in one sentence each

## Related

- [[Notes/Python/Modules and Packages|Modules and Packages]]
- [[Notes/Python/Dependency Management|Dependency Management]]

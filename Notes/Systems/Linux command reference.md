# Linux command reference

Map: [[Maps/Systems|Systems]]

## Summary

Use shell commands to inspect files, processes, permissions, and network state. Paths and available tools vary across distributions.

## Files and text

| Command | Purpose |
| --- | --- |
| `pwd`, `ls`, `cd` | Inspect or change the working directory. |
| `mkdir -p path` | Create a directory and missing parents. |
| `cat`, `less`, `head`, `tail` | Read all or selected parts of a file. |
| `rg pattern path` | Search file contents when ripgrep is installed. |
| `find path -type f -name name` | Find files by filesystem attributes. |
| `>` / `>>` | Redirect output by overwriting / appending. |

## Permissions and processes

- Permissions have owner/group/other groups: read = 4, write = 2, execute = 1.
- `chmod 600 file` allows the owner to read/write; `chmod 700 directory` grants the owner directory access.
- `/etc` commonly contains configuration; `/var` contains changing data such as logs. Logs can also be managed by the system journal.
- `sudo` runs an authorized command with another user's privileges. Check the exact command before elevation.
- `ps` inspects processes; signals request actions such as termination. Avoid assuming every process shuts down safely immediately.

## Network and scheduling

- `dig` inspects DNS; `ping` and `traceroute` provide network diagnostics.
- Traditional cron fields are minute, hour, day-of-month, month, day-of-week, followed by the command.
- A scheduled job has its own execution environment; make paths and logging explicit.

## Related

- [[Notes/Systems/Server provisioning|Server provisioning]]
- [[Notes/Systems/Vim reference|Vim reference]]

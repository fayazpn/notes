# Vim reference

Map: [[Maps/Systems|Systems]]

## Summary

Vim combines modes with composable movements and editing operators.

## Everyday commands

| Command | Action |
| --- | --- |
| `i`, `a`, `o`, `O` | Insert before/after the cursor, or on a new line below/above. |
| `Esc` | Return to Normal mode. |
| `h j k l`, `w`, `gg`, `G` | Move left/down/up/right, by word, to start/end of file. |
| `/text`, `n`, `N` | Search, then next/previous match. |
| `dd`, `yy`, `p`, `u` | Delete a line, yank a line, paste, undo. |
| `v`, `V` | Select characters or lines in Visual mode. |
| `:w`, `:wq`, `:q!` | Save, save and quit, quit without saving. |
| `:reg` | Inspect registers. |
| `Ctrl-o`, `Ctrl-i` | Navigate backward/forward in the jump list. |
| `:help topic` | Read the built-in help. |

Counts compose with operations: `7dd` deletes seven lines. The default yank register is not necessarily the operating-system clipboard.

## Related

- [[Notes/Systems/Linux command reference|Linux command reference]]

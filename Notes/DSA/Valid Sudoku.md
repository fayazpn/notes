# Valid Sudoku

Map: [[Maps/DSA|DSA]]

## Summary

Check that existing digits do not repeat in any row, column, or 3×3 box. This does not solve the puzzle.

## Key points

- Skip empty cells represented by `.`.
- Track separate sets for each row, column, and box. A box is identified by `(row // 3, column // 3)`.
- Return false on a duplicate; return true only after all cells pass.
- A fixed 9×9 board checks 81 cells with bounded storage; do not confuse validation with general Sudoku solving complexity.

## Example

```python
def valid_sudoku(board):
    rows = [set() for _ in range(9)]
    cols = [set() for _ in range(9)]
    boxes = [set() for _ in range(9)]
    for row in range(9):
        for col in range(9):
            value = board[row][col]
            if value == ".":
                continue
            box = (row // 3) * 3 + col // 3
            if value in rows[row] or value in cols[col] or value in boxes[box]:
                return False
            rows[row].add(value)
            cols[col].add(value)
            boxes[box].add(value)
    return True
```

## Related

- [[Notes/DSA/Contains duplicate|Contains duplicate]]

## Sources

- [Original explanation](https://www.youtube.com/watch?v=TjFXEUCMqI8)

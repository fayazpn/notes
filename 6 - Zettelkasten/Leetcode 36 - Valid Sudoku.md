
2024-06-14 20:27

Level: #medium 

Tags: [[ds algo]] [[arrays & hashing]]

# Arrays & Hashing

**Approach 1** 

The approach consists of creating 3 hash-sets for rows, columns, and for sub-matrix of the sudoku
*sub-matrix* is created within the sudoku by indexing row and columns of the sudoku into 3 x 3 of indexes 0, 1, 3

We are hypothetically checking the validity of each rows and columns for these sub-matrices
We add enter hash-map for each row and column, by targeting using formula *(actual index of sudoku // 3, actual index of the sudoku // 3)*
*//* here is floor division where the number is rounded to the closest whole number before the number

- Create hash-set for each row to check for duplicates
- Create hash-set for each column to check for duplicates
- For checking if 3 x 3 matrix is valid is tricky
- Create 9 different sub square of index 0, 1, 2
- Divide the actual index with 3, we get the index of the sub square
 - Create a hash-set to check of 3 x 3 matrix is valid
 - Key is (actual index/ 3, actual index/3)
 - Value is another hash-set

  

- Nested loops of length 9
	- If the value of the board is '.', continue
	- If the board value belongs in the row hash-set or the column hash-set or in the sub matrix hash-set, then return False
	- Else store the value in the hash-set
- If the loop is completed successfully then return False


```python
class Solution(object):
    def isValidSudoku(self, board):
        """
        :type board: List[List[str]]
        :rtype: bool
        """
        rows = collections.defaultdict(set)
        cols = collections.defaultdict(set)
        submatrix = collections.defaultdict(set)
        
        for i in range(9):
            for j in range(9):
                if(board[i][j] == '.'):
                    continue
                    
                if(board[i][j] in rows[i] or 
                board[i][j] in cols[j] or 
                board[i][j] in submatrix[(i // 3, j // 3)]):
                    return False
                    
                rows[i].add(board[i][j])
                cols[j].add(board[i][j])
                submatrix[(i //3, j //3)].add(board[i][j])
        
        return True
```



**Time Complexity *O(9^2)/O(n)***
**Space Complexity O(9^2)/O(n)**

# References

Youtube video solution - https://www.youtube.com/watch?v=TjFXEUCMqI8







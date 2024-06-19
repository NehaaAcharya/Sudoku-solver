# Sudoku-solver
The code uses backtracking to solve the Sudoku puzzle.  

**Class: Solution**

Contains two methods:
isSafe(board, row, col, num): Checks if placing the number num at position (row, col) in the board is safe according to Sudoku rules (no conflicts in row, column, or 3x3 subgrid).
helper(board, row, col): Solves the Sudoku puzzle using backtracking. It tries placing numbers 1 to 9 in each empty cell and recursively checks if it leads to a valid solution.

**Methods:**

isSafe:
Checks the column for the number.
Checks the row for the number.
Checks the 3x3 subgrid containing the cell for the number.
Returns true if placing the number is safe, false otherwise.

helper:
Base case: If the end of the board is reached (all cells filled), it's a valid solution (return true).
It determines the next cell to fill based on current position (row and col).
If the current cell is already filled (not empty), it moves to the next cell.
For an empty cell, it tries all numbers (1 to 9).
For each number, it checks if placing it is safe using isSafe.
If safe, it fills the cell with the number and recursively calls helper to solve the remaining board.
If the recursive call returns true (solution found), it returns true (success).
If none of the numbers work for the cell (placement not safe or doesn't lead to a solution), it backtracks by setting the cell back to empty ('.').
If none of the numbers work for the current cell (no valid placement found), it returns false (no solution found).

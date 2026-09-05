## eightqueens

### Before you start
This is the quest's capstone — no expected function signature to fill in blindly, just a goal: solve the eight queens puzzle and print every solution. Before touching code, make sure you can state the actual rule in one sentence: what does it mean for two queens to "attack" each other on a chessboard?

### What to build
```go
package piscine

func EightQueens() {

}
```
Print every solution to the [eight queens puzzle](https://en.wikipedia.org/wiki/Eight_queens_puzzle) — placing 8 queens on an 8×8 board so none attack each other. Must use recursion.

Each solution is one line, 8 digits, one per column left to right, each digit is that column's queen's row (rows start at 1). Solutions printed in ascending order.

```console
$ go run .
15863724
16837425
17468253
...
```

### Watch for
Checking every possible arrangement of 8 queens (all placements, then filtering) is far too slow — the real technique is to build one column at a time and abandon a placement the moment it's invalid, instead of finishing an invalid board and checking it after.

### Stuck? Ask better
Say how far your solution gets: does it produce zero solutions, some but not all 92, duplicates, or the right count but wrong order? Each of those points at a different part of the logic (the attack check, the recursion's stopping condition, or the ordering of your column-by-column search).

### Hints
<details><summary>Hint 1</summary>
Place one queen per column. For each column, try each row in turn; before committing to a row, check it doesn't attack any queen already placed in earlier columns.
</details>
<details><summary>Hint 2</summary>
Two queens attack each other if they share a row, or if the difference in their columns equals the difference in their rows (that's the diagonal check). Track placed queens' positions as you recurse, and backtrack (undo and try the next row) when no row in a column works.
</details>

### Notions
- [Eight queens puzzle](https://en.wikipedia.org/wiki/Eight_queens_puzzle)
- [Backtracking](https://en.wikipedia.org/wiki/Backtracking)

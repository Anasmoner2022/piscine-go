## fibonacci

### Before you start
This is your first recursive function with *two* recursive calls instead of one — factorial and power only ever called themselves once per step. What does that change about how many base cases you need?

### What to build
```go
func Fibonacci(index int) int {

}
```
Return the value at `index` in the Fibonacci sequence (`0, 1, 1, 2, 3, ...`), index `0` is the first value. Negative index returns `-1`. Recursive, no `for`.

**Usage:**
```go
piscine.Fibonacci(4)
```
```console
$ go run .
3
$
```

### Watch for
The sequence needs *two* previous values to compute the next one — that usually means two base cases (for index `0` and index `1`), not one.

### Stuck? Ask better
Say which index gives a wrong result, and whether it's off by a small, consistent amount (often a sign your base cases are shifted by one position) or wildly wrong (often a sign the recursive formula itself is off).

### Notions
- [Fibonacci sequence](https://en.wikipedia.org/wiki/Fibonacci_sequence)

## recursivefactorial

### Before you start
Same result as `iterativefactorial`, opposite constraint: `for` is forbidden here. What does a function need in order to repeat work without a loop?

### What to build
```go
func RecursiveFactorial(nb int) int {

}
```
Return the factorial of `nb`, using recursion, no `for`. Invalid input or overflow returns `0`.

**Usage:**
```go
piscine.RecursiveFactorial(4)
```
```console
$ go run .
24
$
```

### Watch for
A recursive function needs a stopping point (a base case) or it never ends. What's the smallest input where you already know the answer without any more calculation?

### Stuck? Ask better
If you solved `iterativefactorial`, say what you kept the same (the overflow/invalid-input logic) and what had to change structurally (loop → base case + recursive call). If it's an infinite-recursion crash, that's a missing or wrong base case — say what input triggers it.

### Notions
- [Recursion](https://en.wikipedia.org/wiki/Recursion_(computer_science))

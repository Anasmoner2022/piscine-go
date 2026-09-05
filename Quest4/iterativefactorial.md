## iterativefactorial

### Before you start
This quest introduces a new kind of constraint: not just "make it work," but "make it work this specific way" (iterative here, recursive in the next exercise). What does "iterative" rule out as an approach?

### What to build
```go
func IterativeFactorial(nb int) int {

}
```
Return the factorial of `nb`, using iteration. Invalid input or overflow returns `0`.

**Usage:**
```go
piscine.IterativeFactorial(4)
```
```console
$ go run .
24
$
```

### Watch for
Two separate "return 0" cases are hiding in one requirement: impossible input (like a negative number) and overflow (the true answer exists but doesn't fit in an `int`). Does your solution actually distinguish between those, or does it only handle one?

### Stuck? Ask better
State which case fails: a specific valid input, a specific invalid input, or a large input that should overflow. "Factorial is wrong" isn't enough context — say the input and the exact output you got versus expected.

### Notions
- [Factorial](https://en.wikipedia.org/wiki/Factorial)

## iterativepower

### What to build
```go
func IterativePower(nb int, power int) int {

}
```
Return `nb` to the power of `power`, iteratively. Negative powers return `0`. Overflow doesn't need handling.

**Usage:**
```go
piscine.IterativePower(4, 3)
```
```console
$ go run .
64
$
```

### Watch for
What should `power == 0` return? The spec doesn't say it explicitly — work out the mathematically correct answer and make sure your loop bounds actually produce it (a common off-by-one here is looping `power` times vs. `power - 1` times).

### Stuck? Ask better
Say which specific case is wrong: a normal positive power, the `power == 0` case, or a negative power. Each exercises a different part of your logic.

### Notions
- [Exponentiation](https://en.wikipedia.org/wiki/Exponentiation)

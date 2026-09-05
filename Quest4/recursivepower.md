## recursivepower

### What to build
```go
func RecursivePower(nb int, power int) int {

}
```
Same as `IterativePower`, but recursive — no `for`.

**Usage:**
```go
piscine.RecursivePower(4, 3)
```
```console
$ go run .
64
$
```

### Watch for
What's your base case here — is it `power == 0`, or something else? Get that right first; the recursive step (multiply `nb` by the result of a smaller power) depends on it being correct.

### Stuck? Ask better
If `iterativepower` worked, say what result you're comparing against and which specific input (including `power == 0` and negative powers) breaks in the recursive version.

### Notions
- [Recursion](https://en.wikipedia.org/wiki/Recursion_(computer_science))

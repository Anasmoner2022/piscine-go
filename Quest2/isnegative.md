## isnegative

### What to build
```go
func IsNegative(nb int) {

}
```
Prints `'T'` if `nb` is negative, `'F'` otherwise.

**Usage:**
```go
piscine.IsNegative(1)
piscine.IsNegative(0)
piscine.IsNegative(-1)
```
```console
$ go run .
F
F
T
$
```

### Watch for
Where does `0` fall — negative or not? The expected output already answers that; make sure your condition agrees with it.

### Stuck? Ask better
Show your condition (the `if`/`else` line) and which of the three test cases (`1`, `0`, `-1`) prints wrong. One wrong case usually means the boundary (`0`) is on the wrong side of your comparison.

### Notions
- [01-edu/z01](https://github.com/01-edu/z01)

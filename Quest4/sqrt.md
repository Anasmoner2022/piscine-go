## sqrt

### What to build
```go
func Sqrt(nb int) int {

}
```
Return the square root of `nb` if it's a whole number, otherwise `0`.

**Usage:**
```go
piscine.Sqrt(4)
piscine.Sqrt(3)
```
```console
$ go run .
2
0
$
```

### Watch for
You're working entirely in `int` here — there's no built-in that hands you "is this a perfect square" directly. What's a way to check a candidate answer without ever calculating a non-integer square root?

### Stuck? Ask better
Say what approach you're using to find/check the root, and whether it fails on perfect squares (like `4`), non-perfect squares (like `3`), or both — those point at different bugs.

### Notions
- [Square root](https://en.wikipedia.org/wiki/Square_root)

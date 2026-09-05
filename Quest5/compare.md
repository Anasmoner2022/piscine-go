## compare

### What to build
```go
func Compare(a, b string) int {

}
```
Behave like `strings.Compare`: return `0` if `a == b`, a negative number if `a < b`, a positive number if `a > b`.

**Usage:**
```go
piscine.Compare("Hello!", "Hello!")
piscine.Compare("Salut!", "lut!")
piscine.Compare("Ola!", "Ol")
```
```console
$ go run .
0
-1
1
$
```

### Watch for
"Less than" and "greater than" for strings means lexicographic (dictionary) order, not length. `"Ola!"` being "greater than" `"Ol"` — why, given `"Ol"` is shorter?

### Stuck? Ask better
Say which of the three cases (equal, less-than, greater-than) gives the wrong sign, and what your comparison is actually checking (character-by-character, or something else).

### Notions
- [strings/Compare](https://golang.org/pkg/strings/#Compare)

## index

### What to build
```go
func Index(s string, toFind string) int {

}
```
Return the index of the first occurrence of `toFind` in `s`. Return `-1` if not found. (Behaves like `strings.Index`, but write it yourself.)

**Usage:**
```go
piscine.Index("Hello!", "l")
piscine.Index("Salut!", "alu")
piscine.Index("Ola!", "hOl")
```
```console
$ go run .
2
1
-1
$
```

### Watch for
`toFind` can be more than one character — your search has to check for a full substring match starting at each position, not just a single-character match.

### Stuck? Ask better
Say which case fails: a single-character search, a multi-character search, or the not-found case. Those exercise different parts of your matching logic.

### Notions
- [strings/Index](https://golang.org/pkg/strings/#Index)

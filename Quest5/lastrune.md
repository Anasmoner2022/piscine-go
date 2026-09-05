## lastrune

### Before you start
You could solve this by reusing `nrune` with the right position — what expression gives you "the last index" from a string's length?

### What to build
```go
func LastRune(s string) rune {

}
```
Return the last rune of `s`.

**Usage:**
```go
z01.PrintRune(piscine.LastRune("Hello!"))
z01.PrintRune(piscine.LastRune("Salut!"))
z01.PrintRune(piscine.LastRune("Ola!"))
```
```console
$ go run .
!!!
$
```

### Stuck? Ask better
Show the index expression you're using to find the last position, and what it returns for a specific test string — an off-by-one here (`len(s)` vs. `len(s)-1`) is the most common cause.

### Notions
- [rune-literals](https://golang.org/ref/spec#Rune_literals)

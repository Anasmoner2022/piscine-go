## firstrune

### What to build
```go
func FirstRune(s string) rune {

}
```
Return the first rune of `s`.

**Usage:**
```go
z01.PrintRune(piscine.FirstRune("Hello!"))
z01.PrintRune(piscine.FirstRune("Salut!"))
z01.PrintRune(piscine.FirstRune("Ola!"))
```
```console
$ go run .
HSO
$
```

### Watch for
This returns a `rune`, not a `string` — a single character, printable with `z01.PrintRune` but not directly with `fmt.Println` the way a string would be.

### Stuck? Ask better
Show your return statement and how you're indexing into `s` — a compile error here usually means you're returning a byte or a one-character string instead of an actual `rune`.

### Notions
- [rune-literals](https://golang.org/ref/spec#Rune_literals)

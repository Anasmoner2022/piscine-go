## nrune

### Before you start
This generalizes `firstrune` to any position `n` — and adds a new requirement `firstrune` didn't have: some positions won't exist at all.

### What to build
```go
func NRune(s string, n int) rune {

}
```
Return the `n`th rune of `s`. If that position doesn't exist, return `0`.

**Usage:**
```go
z01.PrintRune(piscine.NRune("Hello!", 3))
z01.PrintRune(piscine.NRune("Salut!", 2))
z01.PrintRune(piscine.NRune("Bye!", -1))
z01.PrintRune(piscine.NRune("Bye!", 5))
z01.PrintRune(piscine.NRune("Ola!", 4))
```
```console
$ go run .
la!
$
```

### Watch for
Two invalid cases are being tested here, not one: negative `n`, and `n` beyond the string's length. Notice the expected output has fewer printed characters than input calls — some calls print nothing visible because they return `0`, not a printable rune.

### Stuck? Ask better
Say which specific call in the usage example produces a wrong result, and whether it's a valid position (indexing bug) or one of the two out-of-range cases (missing bounds check).

### Notions
- [rune-literals](https://golang.org/ref/spec#Rune_literals)

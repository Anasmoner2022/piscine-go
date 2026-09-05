## strlen

### What to build
```go
func StrLen(s string) int {

}
```
Return the number of runes in `s`.

**Usage:**
```go
l := piscine.StrLen("Hello World!")
fmt.Println(l)
```
```console
$ go run .
12
$
```

### Watch for
`len(s)` on a string counts bytes, not runes — for plain ASCII text they're the same, but that's worth knowing now before it bites you later on non-ASCII input.

### Stuck? Ask better
Show your counting approach and the string you tested it on. If the count is off only on certain inputs, say which ones.

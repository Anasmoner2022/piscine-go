## isnumeric

### Before you start
Same shape as `isalpha`, narrower rule — only digits count now, not letters.

### What to build
```go
func IsNumeric(s string) bool {

}
```
Return `true` if `s` contains only numerical characters, `false` otherwise.

**Usage:**
```go
piscine.IsNumeric("010203")
piscine.IsNumeric("01,02,03")
```
```console
$ go run .
true
false
$
```

### Stuck? Ask better
If `isalpha` worked, say exactly what you narrowed in your character check, and which test case breaks.

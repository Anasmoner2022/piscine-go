## atoi

### Before you start
Final step of the `Atoi` progression. Everything from `basicatoi2` still applies, plus: `+` and `-` signs must now be handled correctly.

### What to build
```go
func Atoi(s string) int {

}
```
Convert a string to an `int`, handling `+`/`-` signs. Invalid strings return `0`. No `error` return needed.

**Usage:**
```go
piscine.Atoi("12345")
piscine.Atoi("0000000012345")
piscine.Atoi("012 345")
piscine.Atoi("Hello World!")
piscine.Atoi("+1234")
piscine.Atoi("-1234")
piscine.Atoi("++1234")
piscine.Atoi("--1234")
```
```console
$ go run .
12345
12345
0
0
1234
-1234
0
0
$
```

### Watch for
`"++1234"` and `"--1234"` are the traps here — a single sign is valid, but *two* signs in a row makes the whole string invalid. If your function only checks "is the first character a sign," it won't catch a second one.

### Stuck? Ask better
Say specifically which case fails: single-sign handling (`"+1234"`/`"-1234"`) or double-sign rejection (`"++1234"`/`"--1234"`). Those are two different checks, not one.

### Notions
- [strconv/Atoi](https://golang.org/pkg/strconv/#Atoi)

## basicatoi2

### Before you start
Step two of the `Atoi` progression. Signs still aren't required — but now invalid strings (with non-digit characters) will actually be tested, and must return `0`.

### What to build
```go
func BasicAtoi2(s string) int {

}
```
Same as `BasicAtoi`, but non-digit strings must now return `0` instead of being assumed away.

**Usage:**
```go
piscine.BasicAtoi2("12345")
piscine.BasicAtoi2("0000000012345")
piscine.BasicAtoi2("012 345")
piscine.BasicAtoi2("Hello World!")
```
```console
$ go run .
12345
12345
0
0
$
```

### Watch for
`"012 345"` isn't fully non-digit — it starts valid and breaks partway through. Does your function stop at the first non-digit and return `0` for the whole thing, or does it try to salvage the leading digits? The expected output tells you which.

### Stuck? Ask better
If your basicatoi solution worked, say what you added to detect invalid characters, and which test case (partial-invalid like `"012 345"`, or fully-invalid like `"Hello World!"`) is misbehaving — they can fail for different reasons.

### Notions
- [strconv/Atoi](https://golang.org/pkg/strconv/#Atoi)

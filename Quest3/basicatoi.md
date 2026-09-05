## basicatoi

### Before you start
This is the first of a three-part `Atoi` progression (`basicatoi` → `basicatoi2` → `atoi`), each adding one more real-world messiness. Here, the input is guaranteed clean — no signs, no letters, no spaces, just digits.

### What to build
```go
func BasicAtoi(s string) int {

}
```
Convert a string of digits to its `int` value. No signs. Only valid input will be tested.

**Usage:**
```go
piscine.BasicAtoi("12345")
piscine.BasicAtoi("0000000012345")
piscine.BasicAtoi("000000")
```
```console
$ go run .
12345
12345
0
$
```

### Watch for
Leading zeros shouldn't change the value — make sure your approach doesn't accidentally treat them as meaningful.

### Stuck? Ask better
Show your digit-accumulation logic and which test case (if any) it fails. This is the simplest version — if it's not working, the bug is almost certainly in how you build the number digit by digit, not in edge-case handling.

### Notions
- [strconv/Atoi](https://golang.org/pkg/strconv/#Atoi)

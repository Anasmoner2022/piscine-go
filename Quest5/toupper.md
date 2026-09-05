## toupper

### What to build
```go
func ToUpper(s string) string {

}
```
Return `s` with every letter capitalized.

**Usage:**
```go
piscine.ToUpper("Hello! How are you?")
```
```console
$ go run .
HELLO! HOW ARE YOU?
$
```

### Watch for
Non-letter characters (`!`, `?`, spaces) should pass through unchanged — only actual letters get transformed. Make sure your per-character logic checks for that.

### Stuck? Ask better
Show a specific input/output pair that's wrong, and say whether non-letters are getting mangled or letters aren't being transformed correctly.

### Notions
- [strings/ToUpper](https://golang.org/pkg/strings/#ToUpper)

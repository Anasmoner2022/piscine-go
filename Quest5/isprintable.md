## isprintable

### Before you start
Last of this family — the definition of "printable" is the new thing to look up here, not the loop shape.

### What to build
```go
func IsPrintable(s string) bool {

}
```
Return `true` if `s` contains only printable characters, `false` otherwise.

**Usage:**
```go
piscine.IsPrintable("Hello")
piscine.IsPrintable("Hello\n")
```
```console
$ go run .
true
false
$
```

### Watch for
`\n` (newline) is not printable — it's a control character. What Go standard-library function or character range would you check against to distinguish printable from control characters?

### Stuck? Ask better
Say what specific character or range you're testing each rune against, and which test case is misclassified.

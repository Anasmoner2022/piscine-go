## tolower

### Before you start
Mirror image of `toupper` — if you solved that one, what's the one thing that actually needs to change?

### What to build
```go
func ToLower(s string) string {

}
```
Return `s` with every letter lowercased.

**Usage:**
```go
piscine.ToLower("Hello! How are you?")
```
```console
$ go run .
hello! how are you?
$
```

### Stuck? Ask better
If `toupper` worked, say exactly what you changed for this one and what broke — that isolates the bug fast.

### Notions
- [strings/ToLower](https://golang.org/pkg/strings/#ToLower)

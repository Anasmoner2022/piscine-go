## isalpha

### Before you start
Despite the name, read the spec carefully — this isn't "letters only." It's alphanumeric (letters *and* digits) or empty.

### What to build
```go
func IsAlpha(s string) bool {

}
```
Return `true` if `s` is empty or contains only alphanumeric characters, `false` otherwise.

**Usage:**
```go
piscine.IsAlpha("Hello! How are you?")
piscine.IsAlpha("HelloHowareyou")
piscine.IsAlpha("What's this 4?")
piscine.IsAlpha("Whatsthis4")
```
```console
$ go run .
false
true
false
true
$
```

### Watch for
Spaces count as non-alphanumeric — that's why the first and third examples are `false` despite containing only letters/digits and spaces/punctuation.

### Stuck? Ask better
Say which specific test string gives the wrong result, and whether digits or the empty-string case are the part that's off — this is the first exercise in a family (`isalpha`, `isnumeric`, `islower`, `isupper`) that all share the same loop shape, so nailing the pattern here pays off four times.

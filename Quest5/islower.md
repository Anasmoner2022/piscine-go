## islower

### What to build
```go
func IsLower(s string) bool {

}
```
Return `true` if `s` contains only lowercase characters, `false` otherwise.

**Usage:**
```go
piscine.IsLower("hello")
piscine.IsLower("hello!")
```
```console
$ go run .
true
false
$
```

### Watch for
`"hello!"` is `false` — punctuation fails the check, even though every *letter* in it is lowercase. "Only lowercase characters" means every character, not every letter.

### Stuck? Ask better
Say whether your function is too strict (rejecting valid all-lowercase strings) or too lenient (accepting strings with punctuation/uppercase) — those are opposite bugs.

## basicjoin

### Before you start
Generalizes `concat` from two strings to any number of them, with no separator.

### What to build
```go
func BasicJoin(elems []string) string {

}
```
Return all strings in `elems` concatenated together, in order.

**Usage:**
```go
elems := []string{"Hello!", " How", " are", " you?"}
piscine.BasicJoin(elems)
```
```console
$ go run .
Hello! How are you?
$
```

### Watch for
Building a result with repeated `+=` in a loop works, but for larger slices it's noticeably slower than other approaches Go offers for this — not required to fix now, but worth knowing it exists.

### Stuck? Ask better
Show your loop and what the result looks like for a slice with just one or two elements — that isolates whether the bug is in the looping or in something that only shows up with more elements.

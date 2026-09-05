## join

### Before you start
Same as `basicjoin`, plus one new requirement: a separator between elements — but not before the first or after the last.

### What to build
```go
func Join(strs []string, sep string) string {

}
```
Return all strings in `strs` concatenated, separated by `sep`. (Behaves like `strings.Join`, but write it yourself.)

**Usage:**
```go
toConcat := []string{"Hello!", " How", " are", " you?"}
piscine.Join(toConcat, ":")
```
```console
$ go run .
Hello!: How: are: you?
$
```

### Watch for
A separator after every element (including the last) is a classic off-by-one here. Check your output doesn't have a trailing separator.

### Stuck? Ask better
Say whether the separator is missing somewhere, appearing where it shouldn't (start/end), or the wrong string entirely.

### Notions
- [strings/Join](https://golang.org/pkg/strings/#Join)

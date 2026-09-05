## strrev

### What to build
```go
func StrRev(s string) string {

}
```
Return `s` reversed.

**Usage:**
```go
s := "Hello World!"
s = piscine.StrRev(s)
fmt.Println(s)
```
```console
$ go run .
!dlroW olleH
$
```

### Watch for
Strings in Go aren't directly mutable by index the way slices are — you'll likely need to build the result in a separate structure and convert it back. What type lets you assemble characters in reverse order easily?

### Stuck? Ask better
Show the type you're building the reversed result in, and where it breaks — empty output, wrong order, or a compile error are three different problems.

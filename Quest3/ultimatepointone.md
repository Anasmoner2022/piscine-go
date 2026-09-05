## ultimatepointone

### Before you start
Same goal as `pointone` — set an int to `1` — but now through three layers of indirection instead of one. How many times do you need to dereference to get from `***int` down to the actual `int`?

### What to build
```go
func UltimatePointOne(n ***int) {

}
```
Given a pointer to a pointer to a pointer to an `int`, set the underlying `int` to `1`.

**Usage:**
```go
a := 0
b := &a
n := &b
piscine.UltimatePointOne(&n)
fmt.Println(a)
```
```console
$ go run .
1
$
```

### Watch for
Each `*` peels back one layer. Count the layers in `***int` and make sure you dereference exactly that many times — not one more, not one less.

### Stuck? Ask better
Show the exact dereference chain you wrote (how many `*`s) and the compiler error or wrong value you get. A compile error here almost always means a mismatched dereference count, not a logic bug.

### Notions
- [Pointers](https://golang.org/ref/spec#Pointer_types)

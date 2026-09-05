## ultimatedivmod

### Before you start
Compare this signature to `divmod`'s. What changed, and why might that change the order you read/write `a` and `b` in?

### What to build
```go
func UltimateDivMod(a *int, b *int) {

}
```
Divide the value `a` points to by the value `b` points to. Store the quotient back into `a`, and the remainder into `b`.

**Usage:**
```go
a := 13
b := 2
piscine.UltimateDivMod(&a, &b)
fmt.Println(a)
fmt.Println(b)
```
```console
$ go run .
6
1
$
```

### Watch for
You're overwriting `a` and `b` themselves as part of the calculation. If you divide first but overwrite `a` before you've read `b`'s original value (or vice versa), you'll get a wrong answer using an already-modified input.

### Stuck? Ask better
Show the order in which your function reads and writes `*a` and `*b`. If your remainder is wrong but quotient is right (or vice versa), that's usually a value getting overwritten before it's used.

### Notions
- [Pointers](https://golang.org/ref/spec#Pointer_types)

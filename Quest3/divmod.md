## divmod

### What to build
```go
func DivMod(a int, b int, div *int, mod *int) {

}
```
Divide `a` by `b`. Store the quotient in the `int` pointed to by `div`, and the remainder in the `int` pointed to by `mod`.

**Usage:**
```go
a := 13
b := 2
var div int
var mod int
piscine.DivMod(a, b, &div, &mod)
fmt.Println(div)
fmt.Println(mod)
```
```console
$ go run .
6
1
$
```

### Watch for
`a` and `b` are plain values here — only `div` and `mod` are pointers. Mixing that up (dereferencing `a`, or forgetting to dereference `div`) is the most common mistake.

### Stuck? Ask better
Show your function body and which of `div`/`mod` prints wrong (or both). If both are `0`, you're likely writing to local copies instead of through the pointers.

### Notions
- [Pointers](https://golang.org/ref/spec#Pointer_types)

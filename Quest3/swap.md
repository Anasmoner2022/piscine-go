## swap

### Before you start
This is `pointone`'s idea applied twice, in coordination — you're not setting a fixed value anymore, you're exchanging two.

### What to build
```go
func Swap(a *int, b *int) {

}
```
Swap the values `a` and `b` point to.

**Usage:**
```go
a := 0
b := 1
piscine.Swap(&a, &b)
fmt.Println(a)
fmt.Println(b)
```
```console
$ go run .
1
0
$
```

### Watch for
If you write `*a = *b` and then `*b = *a`, what value does the second line actually copy? Think about ordering — do you need to hold onto one value in a temporary variable first?

### Stuck? Ask better
Show your three (or however many) lines of swapping logic in order. If both values end up the same after swapping, that's a classic "overwrote before saving" bug.

### Notions
- [Pointers](https://golang.org/ref/spec#Pointer_types)

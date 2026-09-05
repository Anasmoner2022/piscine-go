## sortintegertable

### What to build
```go
func SortIntegerTable(table []int) {

}
```
Reorder `table` in ascending order, in place.

**Usage:**
```go
s := []int{5,4,3,2,1,0}
piscine.SortIntegerTable(s)
fmt.Println(s)
```
```console
$ go run .
[0 1 2 3 4 5]
$
```

### Watch for
The function has no return value — the caller's `fmt.Println(s)` prints the *same* slice you modified, not a new one. That means you need to sort the slice's contents directly, not build and return a new sorted slice.

### Stuck? Ask better
Show your sorting approach and the actual output slice. If it prints unchanged, you're likely building a new sorted slice locally instead of mutating `table`'s elements in place.

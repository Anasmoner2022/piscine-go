## pointone

### Before you start
This is your first pointer exercise. In one sentence: what's the difference between changing `n` itself versus changing *what `n` points to*?

### What to build
```go
func PointOne(n *int) {

}
```
Given a pointer to an `int`, set the value it points to `1`.

**Usage:**
```go
n := 0
piscine.PointOne(&n)
fmt.Println(n)
```
```console
$ go run .
1
$
```

### Watch for
`n` inside your function is the address, not the number. What operator lets you reach through the address to change the value at it?

### Stuck? Ask better
Show your function body and what `n` prints as versus what `*n` prints as inside it — that tells us whether you're changing the pointer itself instead of the value behind it.

### Notions
- [Pointers](https://golang.org/ref/spec#Pointer_types)

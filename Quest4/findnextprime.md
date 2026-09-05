## findnextprime

### Before you start
This is `isprime` reused, not reimplemented — the interesting part is what you build *around* it.

### What to build
```go
func FindNextPrime(nb int) int {

}
```
Return the first prime number `≥ nb`. Must be optimized to avoid timeouts.

**Usage:**
```go
piscine.FindNextPrime(5)
piscine.FindNextPrime(4)
```
```console
$ go run .
5
5
$
```

### Watch for
If `nb` itself is already prime, the answer is `nb` — don't start checking from `nb + 1` by default. That's the detail both example calls above are actually testing.

### Stuck? Ask better
If your `isprime` logic is already solid, say specifically whether this fails on `nb` already being prime, or on the search itself never terminating/timing out.

### Notions
- [Prime number](https://en.wikipedia.org/wiki/Prime_number)

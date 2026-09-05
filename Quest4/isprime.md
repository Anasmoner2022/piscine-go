## isprime

### Before you start
This is the first exercise in the quest where "correct" isn't enough on its own — it must also be **fast**. A working-but-slow solution will time out on the tester. Read that as a real constraint, not a suggestion.

### What to build
```go
func IsPrime(nb int) bool {

}
```
Return whether `nb` is prime. Only positive numbers can be prime; `1` is not prime.

**Usage:**
```go
piscine.IsPrime(5)
piscine.IsPrime(4)
```
```console
$ go run .
true
false
$
```

### Watch for
Checking every number from `2` up to `nb - 1` works but is slow for large inputs. A factor pair `(a, b)` where `a * b == nb` always has one factor `≤ √nb` — what does that tell you about how far you actually need to check?

### Stuck? Ask better
If it's giving wrong answers, say which specific number fails and whether `1` and small primes (`2`, `3`) are handled correctly first. If it's timing out, say roughly how large the input is when it times out — that confirms whether it's a correctness bug or a performance one.

### Notions
- [Prime number](https://en.wikipedia.org/wiki/Prime_number)

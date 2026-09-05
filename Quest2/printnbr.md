## printnbr

### Before you start
`int` in Go includes negative numbers, zero, and very large values — and you're told you can't convert to `int64`. What does that restriction rule out as an approach?

### What to build
```go
func PrintNbr(n int) {

}
```
Print any `int` value — every possible value the type allows, including the most negative one.

**Usage:**
```go
piscine.PrintNbr(-123)
piscine.PrintNbr(0)
piscine.PrintNbr(123)
z01.PrintRune('\n')
```
```console
$ go run .
-1230123
$
```

### Watch for
The most negative `int` value is a classic trap: negating it can overflow, because its positive counterpart doesn't fit in the same type. Does your solution handle `math.MinInt` without converting to a bigger type?

### Stuck? Ask better
Say which input breaks it: is it negatives in general, or specifically the minimum possible `int`? Those are different bugs with different fixes.

### Hints
<details><summary>Hint 1</summary>
Print the sign first (if negative), then handle the digits — but think about *when* you flip the sign of `n` versus when you extract digits from it.
</details>
<details><summary>Hint 2</summary>
Extract and print digits one at a time using recursion or a loop on `n / 10` and `n % 10` — but do the digit extraction on the negative number directly (adjusting the modulo sign) rather than negating `n` first.
</details>

### Notions
- [01-edu/z01](https://github.com/01-edu/z01)
- [numeric types](https://golang.org/ref/spec#Numeric_types)

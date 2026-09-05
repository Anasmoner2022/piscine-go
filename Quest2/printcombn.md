## printcombn

### Before you start
This is `printcomb` generalized — instead of always 3 digits, the count is a parameter `n` (0 < n < 10). What about your `printcomb` solution was hardcoded to "3" that now needs to flex?

### What to build
```go
func PrintCombN(n int) {

}
```
Print all combinations of `n` different digits, ascending order.

- n = 1 → `'0, 1, 2, 3, ..., 8, 9'`
- n = 3 → `'012, 013, ..., 689, 789'`

**Usage:**
```go
piscine.PrintCombN(1)
piscine.PrintCombN(3)
piscine.PrintCombN(9)
```
```console
$ go run .
0, 1, 2, 3, 4, 5, 6, 7, 8, 9
012, 013, 014, 015, 016, 017, 018, ... 679, 689, 789
012345678, 012345679, ..., 123456789
$
```

> Be mindful of efficiency — a fixed number of nested loops won't scale to n=9.

### Watch for
Fixed nested loops (like in `printcomb`) only work for a fixed digit count. A variable `n` needs a different shape of solution entirely — what technique lets you go "n levels deep" without writing n loops?

### Stuck? Ask better
Say which `n` value fails (small ones like 1–2, or does it fail/timeout only at large n like 8–9?). That distinguishes a logic bug from a performance problem — they need different fixes.

### Hints
<details><summary>Hint 1</summary>
You can't hardcode n nested loops. What Go construct lets a function call itself to go "one level deeper" each time?
</details>
<details><summary>Hint 2</summary>
Recursion: build a combination one digit at a time. Each recursive call picks the next digit (always larger than the last one picked) and calls itself for the remaining positions, until you've picked `n` digits — then print.
</details>

### Notions
- [01-edu/z01](https://github.com/01-edu/z01)

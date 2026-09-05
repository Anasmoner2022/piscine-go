## atoibase

### Before you start
This is `printnbrbase` in reverse: instead of converting a base-10 `int` into an arbitrary base's string, you're converting an arbitrary base's string back into an `int`. Same validity rules apply to `base`.

### What to build
```go
func AtoiBase(s string, base string) int {

}
```
Return the integer value of `s`, read in `base`. Invalid base returns `0`. Only valid number strings will be tested; negative numbers don't need to be handled.

Validity rules for `base`: at least 2 characters, all unique, no `+`/`-`.

**Usage:**
```go
piscine.AtoiBase("125", "0123456789")
piscine.AtoiBase("1111101", "01")
piscine.AtoiBase("7D", "0123456789ABCDEF")
piscine.AtoiBase("uoi", "choumi")
piscine.AtoiBase("bbbbbab", "-ab")
```
```console
$ go run .
125
125
125
125
0
$
```

### Watch for
Each character of `s` maps to *its position* in `base` — the reverse lookup of what `printnbrbase` does. The last example returns `0` purely because `"-ab"` is an invalid base (contains `-`), regardless of what `s` is.

### Stuck? Ask better
If `printnbrbase` is solid, say what you inverted for this one (going from digit → position, instead of position → digit) and which specific test case gives the wrong number.

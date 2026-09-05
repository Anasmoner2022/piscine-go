## printnbrbase

### Before you start
This is a step up from earlier exercises: the base itself isn't fixed (like binary or hex) — it's an arbitrary string of characters, and part of the exercise is validating that string before you can even start converting.

### What to build
```go
func PrintNbrBase(nbr int, base string) {

}
```
Print `nbr` in the given `base`. If `base` is invalid, print `NV`. Handle negative numbers.

Validity rules for `base`:
- at least 2 characters
- every character unique
- no `+` or `-`

**Usage:**
```go
piscine.PrintNbrBase(125, "0123456789")
piscine.PrintNbrBase(-125, "01")
piscine.PrintNbrBase(125, "0123456789ABCDEF")
piscine.PrintNbrBase(-125, "choumi")
piscine.PrintNbrBase(125, "aa")
```
```console
$ go run .
125
-1111101
7D
-uoi
NV
$
```

### Watch for
The characters of `base` *are* the digits — position `0` in the base string is what prints for a remainder of `0`, position `1` for a remainder of `1`, and so on. That's why base `"choumi"` produces letters like `u`, `o`, `i` instead of numbers.
The last example (`"aa"`) is invalid because the base's two characters aren't unique — make sure your validation actually checks that, not just the length.

### Stuck? Ask better
Say whether the failure is in validation (an invalid base isn't rejected, or a valid one is wrongly rejected) or in the conversion itself (wrong digits, wrong sign) — those are two separate parts of the function, and narrowing to one saves a lot of guessing.

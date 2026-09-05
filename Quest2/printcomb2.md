## printcomb2

### What to build
Print, in ascending order on one line, every combination of two *different* two-digit numbers (`00`–`99`), separated by `, `.

**Usage:**
```console
$ go run . | cat -e
00 01, 00 02, 00 03, ..., 00 98, 00 99, 01 02, 01 03, ..., 97 98, 97 99, 98 99$
$
```

### Watch for
This is `printcomb`'s structure with a different range and width — two positions instead of three, `00`–`99` instead of `0`–`9`. Note the numbers are printed two digits wide even when they're single-digit values (`00`, not `0`).

### Stuck? Ask better
If you solved `printcomb`, say specifically what you changed for this one and what broke — likely candidates: the loop range (0–9 → 0–99) or the zero-padding when printing.

### Notions
- [01-edu/z01](https://github.com/01-edu/z01)

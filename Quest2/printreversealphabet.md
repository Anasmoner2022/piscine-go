## printreversealphabet

### What to build
Print the lowercase Latin alphabet in reverse, `z` to `a`, on a single line. **Casting is not allowed.**

**Usage:**
```console
$ go run .
zyxwvutsrqponmlkjihgfedcba
$
```

### Watch for
No casting means you can't convert to `int` and back to move between letters. What else can move a rune backward through the alphabet, one step at a time?

### Stuck? Ask better
Show the exact line you're using to get from one letter to the previous one, and what error or wrong output you get. If it's a compile error about types, that's the casting restriction biting — say what you tried instead of casting.

### Notions
- [01-edu/z01](https://github.com/01-edu/z01)

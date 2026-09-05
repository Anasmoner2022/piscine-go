## cl-camp3

"Start looking..."

### What to build
Create a file `look` that finds and shows, in the current directory and sub-folders, anything matching **any** of:
- starts with `a`
- ends with `z`
- starts with `z` and ends with `a!`

### Watch for
Three separate conditions joined by OR, not AND — how does `find` express "match any of these patterns"? Test each condition alone before combining.

### Stuck? Ask better
Show which of the three conditions you tested individually and which one is producing wrong results — don't just say "find isn't matching."

### Hint
Read the `find` man page — look for how it combines multiple `-name` tests.

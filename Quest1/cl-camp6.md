## cl-camp6

"Now, do your inventory"

### What to build
Create `countfiles.sh`, which prints **only** the number of regular files and folders in the current directory and its sub-folders (the current directory itself counts too).

**Usage:**
```console
$ ./countfiles.sh | cat -e
12$
$
```

### Watch for
"Only the number" is a real constraint — a command that finds the right files but prints a list, not a count, doesn't satisfy this. What turns a list into a count?
Does the current directory `.` need to be found explicitly, or does it come along automatically?

### Stuck? Ask better
Show the raw list your search produces and the count you're getting — if the count is off by exactly one, that's almost always the current-directory inclusion rule, not a counting bug.

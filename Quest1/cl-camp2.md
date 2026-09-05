## cl-camp2

"Keep training..."

### What to build
Create a file `r` such that running `cat r` prints a single line containing `R`.

**Usage:**
```console
$ cat -e r
R$
$
```

### Watch for
This isn't a script — there's no command to run, just a file. What does `cat` actually do with a file, and what has to be *in* the file for this to work?

### Stuck? Ask better
Show the exact output of `cat -e r` on your file — that `$` marker matters, it shows you exactly where the line ends (or doesn't).

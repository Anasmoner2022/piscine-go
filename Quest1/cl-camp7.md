## cl-camp7

"Be accurate"

### What to build
Create a file named `"\?$*'ChouMi'*$?\"` containing `01` and nothing else.

**Usage:**
```console
$ ls | cat -e
"\?$*'ChouMi'*$?\"$
$
```

### Watch for
The filename contains characters your shell normally treats as special (`$`, `*`, `?`, `"`, `'`). The exercise is really about quoting/escaping, not about the content of the file. Get the filename exactly right before worrying about the content.

### Stuck? Ask better
Show the exact command you ran to create the file and the exact filename `ls` shows back. If they don't match character-for-character, that's a quoting issue — say which characters look different.

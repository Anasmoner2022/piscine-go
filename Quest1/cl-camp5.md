## cl-camp5

"Keep looking..."

### What to build
Create `lookagain.sh`, which searches the current directory and sub-folders for all files ending in `.sh`, and prints only their names — **without** the `.sh` extension — in descending order.

**Usage:**
```console
$ ./lookagain.sh | cat -e
file3$
file2$
file1$
$
```

### Watch for
Two separate transformations are happening: finding the files, then stripping part of each filename. Don't try to solve both in one command if you're not sure how yet — get the file list right first, then work on the trimming.

### Stuck? Ask better
Show the raw list your search produces (before any trimming) and the trimmed result — that tells us whether the problem is in *finding* the right files or in *reformatting* their names.

### Hint
A little `cut`-ing might help — think about what character you're cutting on.

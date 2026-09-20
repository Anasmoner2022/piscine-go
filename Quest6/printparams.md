## printparams

### Before you start
If `printprogramname` needed index `0` of `os.Args`, what's left over that this exercise actually wants?

### What to build
A **program** that prints the arguments received on the command line, one per line — not including the program name itself.

**Usage:**
```console
$ go run . choumi is the best cat
choumi
is
the
best
cat
$
```

### Watch for
If your output includes the program name as an extra first line, you're printing all of `os.Args` instead of just the arguments after it.

### Stuck? Ask better
Show your loop/slice bounds over `os.Args` and whether the mismatch is an extra line at the start, a missing line at the end, or something else.

### Notions
- [os.Args](https://pkg.go.dev/os#pkg-variables)

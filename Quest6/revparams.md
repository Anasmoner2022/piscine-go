## revparams

### Before you start
Same input as `printparams`, different order of output — reuse what you already have for extracting the arguments, and add the reversal on top.

### What to build
A **program** that prints the command-line arguments in reverse order.

**Usage:**
```console
$ go run . choumi is the best cat
cat
best
the
is
choumi
$
```

### Stuck? Ask better
If `printparams` worked, say exactly what you added for the reversal and whether the program name is correctly excluded from it too — reversing the wrong slice (including index `0`) is an easy mistake here.

### Notions
- [os.Args](https://pkg.go.dev/os#pkg-variables)

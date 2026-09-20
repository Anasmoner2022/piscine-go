## printprogramname

### Before you start
This quest is about `os.Args` — the way a Go program sees the command line it was launched with. Before coding: what do you think `os.Args` contains at index `0`?

### What to build
A **program** that prints its own name — whatever the binary was actually called when it ran, not a hardcoded string.

**Usage:**
```console
$ go build
$ ./printprogramname | cat -e
printprogramname$
$ go build -o Nessy
$ ./Nessy
Nessy
$
```

### Watch for
The output changes depending on what the binary is named at build time (`printprogramname` vs `Nessy`) — that's the whole test. If you hardcode the string `"printprogramname"`, it'll pass once and fail the moment the binary is renamed.

### Stuck? Ask better
Say what you're printing and whether it stays fixed even after renaming the binary with `go build -o` — that tells us if you're reading the actual argument or just printing a literal string.

### Notions
- [os.Args](https://pkg.go.dev/os#pkg-variables)

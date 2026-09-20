## printwordstables

### Before you start

The usage example passes the result of [splitwhitespaces](splitwhitespaces.md) into this function. What does each function own?

### What to build

```go
func PrintWordsTables(a []string) {

}
```

Print each element of the string slice `a` on a separate line.

**Usage:**

Here is a possible program to test your function :

```go
package main

import "piscine"

func main() {
	a := piscine.SplitWhiteSpaces("Hello how are you?")
	piscine.PrintWordsTables(a)
}
```

And its output :

```console
$ go run .
Hello
how
are
you?
$
```

### Watch for

- Does an empty element still occupy a line?
- Are you printing the elements themselves or a formatted representation of the whole slice?

### Stuck? Ask better

Show the slice you passed, the per-element output requirement that fails, the actual output with line endings visible, and the last change you tried. Check whether the mismatch already exists in the slice or appears only during printing.

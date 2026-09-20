## concatparams

### Before you start

Compare [join](../Quest5/join.md) with this exercise: what separator is fixed here?

### What to build

```go
func ConcatParams(args []string) string {

}
```

Return all strings in `args` concatenated with a newline (`\n`) between arguments.

**Usage:**

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	test := []string{"Hello", "how", "are", "you?"}
	fmt.Println(piscine.ConcatParams(test))
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

- Does “between” call for a separator after the last argument?
- How do an empty slice and a slice containing an empty string differ?

### Stuck? Ask better

Show the argument slice, the separator requirement that fails, your returned string with newlines made visible, and your last attempted change. Is an extra newline coming from your function or from the caller printing its result?

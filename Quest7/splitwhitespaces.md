## splitwhitespaces

### What to build

```go
func SplitWhiteSpaces(s string) []string {

}
```

Separate the words of `s` into a slice of strings. The separators are spaces, tabs, and newlines.

**Usage:**

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	fmt.Printf("%#v\n", piscine.SplitWhiteSpaces("Hello how are you?"))
}
```

And its output :

```console
$ go run .
[]string{"Hello", "how", "are", "you?"}
$
```

### Watch for

- What happens when several separators occur together or at either end?
- Do you keep the final word when no separator follows it?

### Stuck? Ask better

Show an input with its whitespace escaped, identify the separator or boundary case that fails, show the resulting slice, and describe your last change. Is the missing or extra word tied to repeated whitespace or the end of the string?

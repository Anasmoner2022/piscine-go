## split

### Before you start

Compare [splitwhitespaces](splitwhitespaces.md): here the separator is a supplied string, not one of three whitespace characters.

### What to build

```go
func Split(s, sep string) []string {

}
```

Return the slice of strings produced by splitting `s` by the separator `sep`.

**Usage:**

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	s := "HelloHAhowHAareHAyou?"
	fmt.Printf("%#v\n", piscine.Split(s, "HA"))
}
```

And its output :

```console
$ go run .
[]string{"Hello", "how", "are", "you?"}
$
```

### Watch for

- Are you matching the complete separator, including when it has several characters?
- Can a partial match near the end make you read past the string?

### Stuck? Ask better

Give `s` and `sep`, identify the matching or boundary case that fails, show your returned slice, and describe the last change you tested. Is your code treating a multi-character separator as a whole string or as separate characters?

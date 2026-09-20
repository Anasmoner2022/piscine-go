## any

### Before you start

Compare [map](map.md): here the callback accepts strings, and the return value answers one question about the whole slice.

### What to build

```go
func Any(f func(string) bool, a []string) bool {

}
```

Return `true` if `f` returns `true` for at least one element of the string slice `a`; otherwise return `false`.

**Usage:**

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	a1 := []string{"Hello", "how", "are", "you"}
	a2 := []string{"This", "is", "4", "you"}

	result1 := piscine.Any(piscine.IsNumeric, a1)
	result2 := piscine.Any(piscine.IsNumeric, a2)

	fmt.Println(result1)
	fmt.Println(result2)
}
```

And its output :

```console
$ go run .
false
true
$
```

### Watch for

- Does a later non-match undo an earlier match?
- Can an empty slice contain a matching element?

### Stuck? Ask better

Identify the failing stage: testing an individual string or combining the callback results. Show the callback and slice, the individual results and final result, and your last change. Does the answer change incorrectly when the only match moves within the slice?

### Notions

- [Function literals](https://golang.org/ref/spec#Function_literals)
- [Function declaration](https://golang.org/ref/spec#Function_declarations)
- [Function types](https://golang.org/ref/spec#Function_types)

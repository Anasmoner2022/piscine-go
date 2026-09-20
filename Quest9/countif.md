## countif

### Before you start

Compare [any](any.md): finding one match answers that exercise, but what information does this return value require?

### What to build

```go
func CountIf(f func(string) bool, tab []string) int {

}
```

Return the number of elements of `tab` for which `f` returns `true`.

**Usage:**

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	tab1 := []string{"Hello", "how", "are", "you"}
	tab2 := []string{"This","1", "is", "4", "you"}
	answer1 := piscine.CountIf(piscine.IsNumeric, tab1)
	answer2 := piscine.CountIf(piscine.IsNumeric, tab2)
	fmt.Println(answer1)
	fmt.Println(answer2)
}
```

And its output :

```console
$ go run .
0
2
$
```

### Watch for

- Are you counting matching elements or counting every callback call?
- If the same matching string appears twice, how many elements match?

### Stuck? Ask better

Name the failing stage: evaluating `f`, deciding whether an element matches, or accumulating the count. Provide the callback and slice, the per-element results and final count, and your last change. Check whether the first match prevents later matches from being counted.

### Notions

- [Function literals](https://golang.org/ref/spec#Function_literals)
- [Function declaration](https://golang.org/ref/spec#Function_declarations)
- [Function types](https://golang.org/ref/spec#Function_types)

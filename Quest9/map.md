## map

### Before you start

Compare [foreach](foreach.md): the callback now returns a boolean, and your function must collect those results.

### What to build

```go
func Map(f func(int) bool, a []int) []bool {

}
```

Apply `f`, of type `func(int) bool`, to each element of `a`. Return a boolean slice containing all the return values in the corresponding input order.

**Usage:**

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	a := []int{1, 2, 3, 4, 5, 6}
	result := piscine.Map(piscine.IsPrime, a)
	fmt.Println(result)
}
```

And its output :

```console
$ go run .
[false true true false true false]
$
```

### Watch for

- Does each input element have a corresponding result, including when that result is `false`?
- Are results kept in the same order as their inputs?

### Stuck? Ask better

Name the failing stage: invoking the callback, obtaining its result, or collecting results. Show the callback and input slice, the returned slice, and your last change. Check whether a missing `false` comes from the callback or from how you store its result.

### Notions

- [Function literals](https://golang.org/ref/spec#Function_literals)
- [Function declaration](https://golang.org/ref/spec#Function_declarations)
- [Function types](https://golang.org/ref/spec#Function_types)

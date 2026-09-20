## advancedsortwordarr

### Before you start

Compare [sortwordarr](sortwordarr.md): the caller now supplies the comparison rule. Recall the comparison-result convention from [issorted](issorted.md).

### What to build

```go
func AdvancedSortWordArr(a []string, f func(a, b string) int) {

}
```

Sort the string slice `a` according to the function `f` passed as an argument. The supplied slice must reflect the resulting order.

**Usage:**

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {

	result := []string{"a", "A", "1", "b", "B", "2", "c", "C", "3"}
	piscine.AdvancedSortWordArr(result, piscine.Compare)

	fmt.Println(result)
}
```

And its output :

```console
$ go run .
[1 2 3 A B C a b c]
$
```

### Watch for

- Does every ordering decision follow `f`, even when its order differs from ASCII order?
- How do equal elements affect your rearrangement logic?

### Stuck? Ask better

Identify the failing stage: the comparator, interpreting its result, or rearranging the slice. Supply the comparator and input, the slice after the call, and your last change. If the example works but a different comparator fails, locate any ordering decision that bypasses `f`.

### Notions

- [Function literals](https://golang.org/ref/spec#Function_literals)
- [Function declaration](https://golang.org/ref/spec#Function_declarations)
- [Function types](https://golang.org/ref/spec#Function_types)

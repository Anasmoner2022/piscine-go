## makerange

### Before you start

Compare this with [appendrange](appendrange.md): the range and nil-result rules stay the same, but the forbidden operation changes.

### What to build

```go
func MakeRange(min, max int) []int {

}
```

Return the integers from `min` (included) to `max` (excluded) as an `[]int`. Return a `nil` slice when `min >= max`. **`append` is forbidden.**

**Usage:**

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	fmt.Println(piscine.MakeRange(5, 10))
	fmt.Println(piscine.MakeRange(10, 5))
}
```

And its output :

```console
$ go run .
[5 6 7 8 9]
[]
$
```

### Watch for

- How many elements belong in a valid range, and which indices can you write?
- What happens before allocation when the range is empty or reversed?

### Stuck? Ask better

Give the range you tested, the constraint that fails, your observed result or panic, and the last change you tried. Distinguish a length/indexing problem from returning the wrong kind of empty slice without `append`.

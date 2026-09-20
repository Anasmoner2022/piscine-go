## appendrange

### What to build

```go
func AppendRange(min, max int) []int {

}
```

Return the integers from `min` (included) to `max` (excluded) as an `[]int`. Return a `nil` slice when `min >= max`. **`make` is forbidden.**

**Usage:**

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	fmt.Println(piscine.AppendRange(5, 10))
	fmt.Println(piscine.AppendRange(10, 5))
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

- Does your last element respect the excluded upper bound?
- A nil slice and an allocated empty slice can both print as `[]`. How will you check the required distinction?

### Stuck? Ask better

Name the range you tried, the specific requirement that fails, the result you observed, and the last change you tested. Is the problem the upper bound, the nil result, or working without `make`?

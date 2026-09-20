## issorted

### Before you start

The callback now compares two integers instead of classifying one element. What does the sign of its result tell you?

### What to build

```go
func IsSorted(f func(a, b int) int, a []int) bool {

}
```

Return `true` if the integer slice `a` is sorted, otherwise `false`. The supplied comparator returns a positive integer when its first argument is greater than its second, `0` when equal, and a negative integer otherwise. Write your own `f` function for testing; the usage program deliberately omits it.

**Usage:**

Here is a possible program to test your function (without `f`):

```go
package main

import (
	"fmt"
)

func main() {
	a1 := []int{0, 1, 2, 3, 4, 5}
	a2 := []int{0, 2, 1, 3}

	result1 := IsSorted(f, a1)
	result2 := IsSorted(f, a2)

	fmt.Println(result1)
	fmt.Println(result2)
}
```

And its output:

```console
$ go run .
true
false
$
```

### Watch for

- Are you checking the sign of the comparator result or assuming it is exactly `-1` or `1`?
- What does an equal pair tell you about the ordering of the remaining elements?

### Stuck? Ask better

Identify the failing stage: your test comparator, selecting pairs to compare, or deciding whether the results describe a sorted slice. Show the slice and comparator, the comparison results and final boolean, and your last change. Point to the first comparison whose interpretation is wrong.

### Notions

- [Function literals](https://golang.org/ref/spec#Function_literals)
- [Function declaration](https://golang.org/ref/spec#Function_declarations)
- [Function types](https://golang.org/ref/spec#Function_types)

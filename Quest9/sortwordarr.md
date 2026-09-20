## sortwordarr

### Before you start

Compare `sortparams`: here you receive a slice to modify instead of printing command-line arguments.

### What to build

```go
func SortWordArr(a []string) {

}
```

Sort the string slice `a` in ascending ASCII order. The caller must see the sorted elements in the supplied slice.

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
	piscine.SortWordArr(result)

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

- Does your ordering agree with the example's digits, uppercase letters, and lowercase letters?
- Can the caller see the changes, or did you only change a separate slice?

### Stuck? Ask better

Name the failing stage: comparing strings, rearranging elements, or making the changes visible to the caller. Show the input slice, its contents after the call, and your last change. Is the order wrong, or is the original slice unchanged?

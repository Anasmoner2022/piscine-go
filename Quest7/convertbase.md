## convertbase

### Before you start

Compare [atoibase](../Quest5/atoibase.md) and [printnbrbase](../Quest5/printnbrbase.md): which ideas carry over, and how does returning a string change the task?

### What to build

```go
func ConvertBase(nbr, baseFrom, baseTo string) string {

}
```

Return `nbr`, a string representing a numeric value in [base](https://simple.wikipedia.org/wiki/Base_(mathematics)) `baseFrom`, represented in `baseTo`. Only valid bases are tested; negative numbers are not tested.

**Usage:**

Here is a possible program to test your function :

```go
package main

import (
	"fmt"
	"piscine"
)

func main() {
	result := piscine.ConvertBase("101011", "01", "0123456789")
	fmt.Println(result)
}
```

And its output :

```console
$ go run .
43
$
```

### Watch for

- Are digits interpreted by their positions in the supplied alphabet?
- What represents zero when the target alphabet does not contain the character `0`?

### Stuck? Ask better

Provide `nbr` and both alphabets, identify the conversion case that fails, show expected versus actual output, and state your last change. Does the failure depend on zero, a particular alphabet, or the target base size?

### Hints

<details>
<summary>Hint 1</summary>

Separate understanding the source representation from expressing the value in the target representation.

</details>

<details>
<summary>Hint 2</summary>

Check the boundary between those two stages independently. A correct numeric value can still be formatted incorrectly, especially for zero.

</details>

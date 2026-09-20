## foreach

### What to build

```go
func ForEach(f func(int), a []int) {

}
```

Apply the function `f` to each element of the integer slice `a`.

**Usage:**

Here is a possible program to test your function :

```go
package main

import "piscine"

func main() {
	a := []int{1, 2, 3, 4, 5, 6}
	piscine.ForEach(piscine.PrintNbr, a)
}
```

And its output :

```console
$ go run .
123456
$
```

### Watch for

- Are you passing the function itself or trying to pass the result of calling it?
- Does your function add any output that the callback did not request?

### Stuck? Ask better

Identify the failing stage: passing the callback, supplying an element to it, or the callback's own behavior. Show the callback and slice, the observed calls or output, and your last change. Does the callback work when tested directly with one element?

### Notions

- [Function literals](https://golang.org/ref/spec#Function_literals)
- [Function declaration](https://golang.org/ref/spec#Function_declarations)
- [Function types](https://golang.org/ref/spec#Function_types)

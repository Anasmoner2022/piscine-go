## bool

### Before you start

The supplied `bool` link is unavailable; the current upstream subject is [boolean](https://github.com/01-edu/public/tree/master/subjects/boolean/README.md). This file keeps the requested exercise-list name; the program directory remains `boolean` as specified upstream.

### What to build

Create a directory named `boolean`, copy the starter code below into `boolean/main.go`, and make the necessary changes so the program works.

**Code to be copied:**

```go
func printStr(s string) {
	for _, r := range s {
		z01.PrintRune(r)
	}
	z01.PrintRune('\n')
}

func isEven(nbr int) boolean {
	if even(nbr) == 1 {
		return yes
	} else {
		return no
	}
}

func main() {
	if isEven(lengthOfArg) == 1 {
		printStr(EvenMsg)
	} else {
		printStr(OddMsg)
	}
}
```

**Usage:**

```console
$ go run . "not" "odd"
I have an even number of arguments
$ go run . "not even"
I have an odd number of arguments
```

### Watch for

- Which identifiers in the starter have no declaration yet?
- Is the program name part of the argument count described by the messages?
- Do the values returned by `isEven` agree with the comparison used in `main`?

### Stuck? Ask better

Name the failing stage: declarations and compilation, argument counting, parity checking, or message output. Show its input, the error or result it produces, and the smallest change you tried. If it compiles but prints the wrong message, trace the count before changing the output stage.

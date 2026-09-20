## doop

### What to build

Write a program called `doop` taking exactly three arguments: a value, one of `+`, `-`, `/`, `*`, `%`, and another value. Print nothing for an invalid operator, invalid value, wrong number of arguments, or overflow. Handle division and modulo by zero with the exact messages shown below.

**Usage:**

```console
$ go run .
$ go run . 1 + 1 | cat -e
2
$
$ go run . hello + 1
$ go run . 1 p 1
$ go run . 1 / 0 | cat -e
No division by 0
$
$ go run . 1 % 0 | cat -e
No modulo by 0
$
$ go run . 9223372036854775807 + 1
$ go run . -9223372036854775809 - 3
$ go run . 9223372036854775807 "*" 3
$ go run . 1 "*" 1
1
$ go run . 1 "*" -1
-1
$
```

### Watch for

- Can a failed value conversion be mistaken for a valid zero?
- Can valid operands still produce an overflowing result?
- Does any invalid path print partial output before it has been fully checked?

### Stuck? Ask better

Identify the failing stage: checking arguments, parsing values, selecting the operation, checking arithmetic, or printing. Provide the exact command, the observed output, and the last change you tried. For a boundary failure, distinguish an operand that cannot be represented from a result that overflows.

### Hints

<details>
<summary>Hint 1</summary>

Separate input validity from arithmetic validity; passing the first check does not establish the second.

</details>

<details>
<summary>Hint 2</summary>

Consider each operator's boundaries before producing output. Division and modulo also have explicitly required zero cases.

</details>

### Notions

- [Numeric Types](https://golang.org/ref/spec#Numeric_types)
- [Arithmetic Operators](https://golang.org/ref/spec#Arithmetic_operators)

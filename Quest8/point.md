## point

### Before you start

How does the pointer passed to `setPoint` relate to the value printed in `main`?

### What to build

Create a directory named `point`. Copy the starter code below into `point/main.go` and make the necessary changes so it works. `setPoint()` must work with `int`.

**Code to be copied:**

```go
func setPoint(ptr *point) {
	ptr.x = 42
	ptr.y = 21
}

func main() {
	points := &point{}

	setPoint(points)

	fmt.Printf("x = %d, y = %d\n",points.x, points.y)
}
```

**Usage:**

```console
$ go run .
x = 42, y = 21
$
```

### Watch for

- What fields and types does the starter code expect `point` to have?
- Is the object modified by `setPoint` the same one inspected by `main`?

### Stuck? Ask better

Identify the failing stage: declaring the type, creating the value, modifying it through the pointer, or printing it. Show the relevant input or declaration, the observed error or field values, and your last attempted change. Locate where the values first differ from the example.

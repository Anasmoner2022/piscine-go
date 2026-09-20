## displayfile

### What to build

Write a program that displays the contents of the file named by its argument on standard output. With no file argument, print `File name missing`; with more than one, print `Too many arguments`, as shown below.

**Usage:**

```console
$ go run .
File name missing
$ echo 'Almost there!!' > quest8.txt
$ go run . quest8.txt main.go
Too many arguments
$ go run . quest8.txt
Almost there!!
```

### Watch for

- Is argument validation complete before you try to open a file?
- Does your output preserve the file's contents, including its existing line endings?
- When is the opened file closed?

### Stuck? Ask better

Identify the failing stage: argument validation, opening, reading, or output. Give the command and relevant file contents, show the error or output, and describe your last change. Establish whether the correct bytes were read before investigating how they were printed.

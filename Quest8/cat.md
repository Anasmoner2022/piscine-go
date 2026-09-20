## cat

### Before you start

Extend the idea from [displayfile](displayfile.md): how does the input source change when there are several file arguments or none?

### What to build

Write a simplified `cat` program. Options do not need to be handled. Display the given files as in the examples; when called without arguments, read standard input (stdin) and print it back to standard output (stdout). Preserve the demonstrated error behavior.

**Usage:**

```console
$ echo '"Programming is a skill best acquired by practice and example rather than from books" by Alan Turing' > quest8.txt
$ cat <<EOF> quest8T.txt
"Alan Mathison Turing was an English mathematician, computer scientist, logician, cryptanalyst. Turing was highly influential in the development of theoretical computer science, providing a formalisation of the concepts of algorithm and computation with the Turing machine, which can be considered a model of a general-purpose computer. Turing is widely considered to be the father of theoretical computer science and artificial intelligence."
EOF
$ go run . abc
ERROR: open abc: no such file or directory
exit status 1
$ go run . quest8.txt
"Programming is a skill best acquired by pratice and example rather than from books" by Alan Turing
$ go run . quest8.txt abc
"Programming is a skill best acquired by pratice and example rather than from books" by Alan Turing
ERROR: open abc: No such file or directory
$ cat quest8.txt | ./cat
"Programming is a skill best acquired by pratice and example rather than from books" by Alan Turing
$ go run .
Hello
Hello
^C
$ go run . quest8.txt quest8T.txt
"Programming is a skill best acquired by pratice and example rather than from books" by Alan Turing
"Alan Mathison Turing was an English mathematician, computer scientist, logician, cryptanalyst. Turing was highly influential in the development of theoretical computer science, providing a formalisation of the concepts of algorithm and computation with the Turing machine, which can be considered a model of a general-purpose computer. Turing is widely considered to be the father of theoretical computer science and artificial intelligence."
$
```

### Watch for

- Can the same reading/output stage work with either a file or stdin?
- Are you preserving the input's line endings instead of adding your own?
- Upstream's examples contain `practice`/`pratice` and error-capitalization inconsistencies; they are reproduced unchanged below.

### Stuck? Ask better

Name the failing stage: choosing the input source, opening a file, reading, writing, or reporting an error. Show the command and input, the observed output or exit status, and the last change you tried. Say whether the same failure occurs with a file and with stdin.

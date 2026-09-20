## sortparams

### Before you start
"ASCII order" is the detail to get right here — look at the expected output below before assuming this is the same as normal dictionary sorting.

### What to build
A **program** that prints the command-line arguments sorted in ASCII order.

**Usage:**
```console
$ go run . 1 a 2 A 3 b 4 C
1
2
3
4
A
C
a
b
$
```

### Watch for
Digits come before uppercase letters, which come before lowercase letters, in ASCII — that's why `A` and `C` print before `a` and `b` even though `a` comes first in the alphabet. If you're sorting case-insensitively, this output won't match.

### Stuck? Ask better
Show a specific pair of arguments that sort in the wrong order relative to each other, and what comparison your sort is using — a case-insensitive comparison is the most likely culprit if uppercase/lowercase are mixed together.

### Notions
- [ASCII table](https://en.wikipedia.org/wiki/ASCII#Character_set)

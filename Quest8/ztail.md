## ztail

### Before you start

Compare [cat](cat.md): this program selects the end of each file and must continue processing after file errors.

### What to build

Write a simplified `tail` program taking at least one file. Handle only `-c`: all tests use it as the first argument, with a positive value. The `os` package is allowed. On errors, process all files but return a non-zero exit status. For multiple files, print the filenames and separating newlines exactly as demonstrated below.

**Usage:**

If `file1.txt` & `file2.txt` contains :

```
abcdefghijklmnopqrstuvwxyz

```

**Note** that the files above end with a new line.

Normal cases :

```console
$ go run . -c 4 file1.txt
xyz
$ go run . -c 4 file1.txt file2.txt
==> file1.txt <==
xyz

==> file2.txt <==
xyz
$
```

Error cases :

```console
$ go run . -c 4 file1.txt nonexisting1.txt file2.txt nonexisting2.txt
==> file1.txt <==
xyz
open nonexisting1.txt: no such file or directory

==> file2.txt <==
xyz
open nonexisting2.txt: no such file or directory
$ echo $?
1
$
```

### Watch for

- `-c` counts bytes: how does the file's final newline affect the selected suffix?
- What if the requested count exceeds the file's length?
- Can a later successful file accidentally erase an earlier failure status?

### Stuck? Ask better

Identify the failing stage: reading the count, opening/reading a file, selecting its suffix, printing headers, or setting the final status. Supply the command and file contents, show the output and status, and describe your last change. For mixed valid and missing files, point to the first stage that stops behaving correctly.

### Hints

<details>
<summary>Hint 1</summary>

Check a single file's selected bytes before adding multiple-file formatting.

</details>

<details>
<summary>Hint 2</summary>

Treat each file's processing result and the whole program's final status as separate concerns; an error must not prevent later files from being processed.

</details>

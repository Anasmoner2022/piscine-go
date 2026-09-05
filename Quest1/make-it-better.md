## make-it-better

### Before you start
In one sentence: what does this exercise actually want you to produce? (Hint: it's not the `ls` output — it's the *files* that make that output true.)

### What to build
Create files and directories such that this exact command produces the output shown below:

```console
$ TZ=utc ls -l --time-style='+%F %R' | sed 1d | awk '{print $1, $6, $7, $8, $9, $10}'
dr-------x 1986-01-05 00:00 0
-r------w- 1986-11-13 00:01 1
-rw----r-- 1988-03-05 00:10 2
lrwxrwxrwx 1990-02-16 00:11 3 -> 0
-r-x--x--- 1990-10-07 01:00 4
-r--rw---- 1990-11-07 01:01 5
-r--rw---- 1991-02-08 01:10 6
-r-x--x--- 1991-03-08 01:11 7
-rw----r-- 1994-05-20 10:00 8
-r------w- 1994-06-10 10:01 9
dr-------x 1995-04-10 10:10 A
$
```

**Mac users:** you need GNU Core Utilities, and the command becomes `TZ=utc gls -l ...`. Your mode column may render slightly differently (e.g. `lrwxr-xr-x` instead of `lrwxrwxrwx`) — that's fine.

Each row tells you three things about one file/directory: its **permissions**, its **timestamp**, and its **name**. Read all three columns as one instruction, not separately.

### Watch for
- The date/time isn't decoration — it's something you have to *set* on the file.
- One entry is a symlink (`->`). What command creates that?

### Stuck? Ask better
Give the exact `ls -l` line you're trying to match, the line your current file actually produces, and which column (permissions, date, or name) is wrong. Don't paste your whole directory — isolate the one file that's off first.

### Submit
```
tar -cf done.tar *
```
Only `done.tar` gets submitted.

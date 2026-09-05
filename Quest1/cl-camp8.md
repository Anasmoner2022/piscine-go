## cl-camp8

"Pick your equipment"

### What to build
Write a command line in `skip.sh` that prints the result of `ls -l`, skipping every other line — starting **with** the first one (so the first line is skipped, kept, skipped, kept...).

### Watch for
"Starting with the first one" is the detail that decides odd vs. even line selection — read it twice before picking your pattern.

### Stuck? Ask better
Show which lines your command is keeping vs. which it should keep, numbered — that pinpoints whether you have an off-by-one in the pattern rather than a wrong tool choice.

### Hint
`awk` or `sed` can do this — both have a way to act on every Nth line.

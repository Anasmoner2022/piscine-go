## cl-camp1

"Now that you know who you are, you need to remember what you can do..."

### What to build
Write, in a file `mastertheLS`, one command line that:
- lists files and directories in the current directory
- ignores hidden files, `.`, and `..`
- separates results with commas **only**
- orders them newest-first by access time
- appends `/` to directory names

### Watch for
Five requirements, one command. Which `ls` flags handle sorting and formatting? Which flag adds the trailing `/`? Test each requirement in isolation before combining them.

### Stuck? Ask better
Run your command and show its actual output next to what the five requirements demand — then say specifically which requirement is failing (order, separator, hidden files, or the trailing slash). "It doesn't match" isn't specific enough to debug.

### Hint
Read the `ls` man page — specifically the flags for sort order, format, and file-type indicators.

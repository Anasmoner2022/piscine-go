## capitalize

### Before you start
This combines `toupper` and `tolower`'s ideas, but the tricky part is deciding *where* a word starts — the spec defines a word as a run of alphanumeric characters, which includes numbers, not just letters.

### What to build
```go
func Capitalize(s string) string {

}
```
Capitalize the first letter of each word, lowercase the rest of each word. Non-alphanumeric characters (including `+`) are word separators, left unchanged.

**Usage:**
```go
piscine.Capitalize("Hello! How are you? How+are+things+4you?")
```
```console
$ go run .
Hello! How Are You? How+Are+Things+4you?
$
```

### Watch for
Look closely at `4you` in the expected output — it stays `4you`, not `4You`. A word starting with a digit doesn't get its first *letter* capitalized at position 0, because position 0 isn't a letter. What does "capitalize the first letter" actually mean when the first character of a word is a digit?

### Stuck? Ask better
Show a specific word from your output that's wrong, and say whether the issue is detecting where a new word starts, or the capitalization/lowering itself once a word is found.

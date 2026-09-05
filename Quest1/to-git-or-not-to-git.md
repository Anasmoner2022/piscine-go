## to-git-or-not-to-git

### Before you start
What does the raw JSON at that URL look like *before* you try to extract anything from it? Look first, filter second.

### What to build
Write `to-git-or-not-to-git.sh`: one command line that prints the `name`, `power`, and `gender` of the superhero with `id: 170`, sourced from:

`https://((DOMAIN))/assets/superhero/all.json`

**Usage:**
```console
$ bash to-git-or-not-to-git.sh
Chameleon
28
Male
$
```

### Watch for
- The file is a list of heroes — how do you select the one with a specific `id`?
- `jq` can output multiple fields on separate lines in one call. Don't chain three separate `curl` calls.

### Stuck? Ask better
Paste the exact `jq` filter you tried and what it printed instead of the expected output. If it's empty output, that usually means your `id` filter didn't match anything — check the type (string vs. number) before assuming `jq` syntax is wrong.

### Hint
`curl` the URL, pipe into `jq`.

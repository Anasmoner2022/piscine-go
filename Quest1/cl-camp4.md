## cl-camp4

"Someone familiar..."

### Before you start
This is a step up from `who-are-you` — the field you need (`relatives`) is nested, not top-level. Look at the raw JSON structure for one hero before writing your filter.

### What to build
Create `myfamily.sh`, which prints a subject's family (the `relatives` field), with quotes removed. The subject's `id` comes from the environment variable `HERO_ID`.

Source: `https://((DOMAIN))/assets/superhero/all.json`
Tools: `curl`, `jq`, and others

**Usage:**
```console
$ export HERO_ID=1
$ ./myfamily.sh
Marlo Chandler-Jones (wife); Polly (aunt); Mrs. Chandler (mother-in-law); Keith Chandler, Ray Chandler, three unidentified others (brothers-in-law); unidentified father (deceased); Jackie Shorr (alleged mother; unconfirmed)
$
```

### Watch for
- `HERO_ID` is read from the environment, not hardcoded — make sure your `jq` filter actually uses the variable.
- The output has no surrounding quotes even though the raw JSON field is a quoted string.

### Stuck? Ask better
Paste your `jq` filter, the raw field value from the JSON for your test ID, and your script's actual output. If quotes are still showing up, that's the same fix as `who-are-you` — apply what you learned there.

## who-are-you

"You just woke up in a dark alley. You can't remember who you are. The only thought in your mind: `subject Id: 70`."

### Before you start
What's different here from `to-git-or-not-to-git`? (Same source, same tools — but the output format isn't a bare value this time.)

### What to build
Create `who-are-you.sh`, which prints your name — and *only* your name — exactly as shown below, using `id: 70`.

Source: `https://((DOMAIN))/assets/superhero/all.json`
Tools: `curl`, `jq`

**Usage:**
```console
$./who-are-you.sh | cat -e
"name"$
$
```

### Watch for
Look closely at the expected output — it includes the quotation marks. That tells you something about how much `jq` is doing versus how much you need to strip yourself.

### Stuck? Ask better
Show your exact `jq` filter and its raw output. If your output is missing the quotes or has extra ones, that's a `jq` flag issue (`-r` strips them) — say which one you're using.

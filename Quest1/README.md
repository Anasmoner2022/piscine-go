## Introduction

### 1 — get-ready

Create in your [Gitea](https://((DOMAIN))/git) account the repository named `((ROOT))`. This is where every exercise you submit will live.

Once created, clone it to your desktop. Open a Unix shell (Git Bash on Windows) and tell Git to remember your password:

```
git config --global credential.helper store
```

Then clone (replace `choumi` with your own username):

```
git clone https://((DOMAIN))/git/choumi/((ROOT)).git
```

### 2 — set

Write your first shell script, `hello.sh`. When run, it must print `Hello choumi!`, where `choumi` is *your* username.

**Usage** (if your username is `choumi`):
```console
$ bash hello.sh
Hello choumi!
$
```

### 3 — go-say-hello

Push it:
```
git add hello.sh
git commit -m "My very first commit"
git push
```

Then click "RUN INTRODUCTION TEST" on the platform.

### Stuck? Ask better
If `git push` or the test fails, don't just say "it doesn't work." Say: the exact command you ran, the exact error text, and whether `git clone` succeeded earlier. 90% of Introduction problems are auth or path issues — check those first before assuming your script is wrong.

### Recommendation
Each quest has a hint video. Watch it as you go — subtitles available in French and English.

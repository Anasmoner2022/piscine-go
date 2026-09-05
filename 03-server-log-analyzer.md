## Project — Server Log Analyzer

**Team size:** 4
**Type:** CLI application, Go

---

### Before you start (as a team)

Restate the goal out loud, all four of you: *what does this program turn into what?* (Raw log lines → structured data → aggregated statistics → a filtered/ranked report.) This project is a straight pipeline, more so than the first two — get clear now on where one stage ends and the next begins, because that boundary is your integration contract.

Write it down: one sentence per person, "I own ___, I hand off ___ to ___."

### Objective

A CLI tool that reads a server log file and turns hundreds or thousands of raw lines into a useful summary — request counts, status codes, errors, and top endpoints — instead of making a human read the file by hand.

```
192.168.1.10 - GET /home 200
192.168.1.20 - GET /login 200
192.168.1.15 - POST /login 401
192.168.1.30 - GET /admin 500
```
becomes:
```
Total Requests: 4

Status Codes:
200: 2
401: 1
500: 1

Errors: 2

Most Requested Endpoints:
/login: 2
/home: 1
/admin: 1
```

### Core requirements

- Read a log file and process it line by line
- Parse each line into its fields (IP, method, endpoint, status code)
- Count total requests, status-code frequency, error count, endpoint frequency, IP frequency
- Support filtering (e.g. only errors, only a given endpoint) and ranking (e.g. top N endpoints)
- Produce a readable report
- Handle malformed lines without crashing the whole run

### Build it in levels

**Level 1 — Read the file.** Open a log file, read its content, count lines. Prove you can reliably get the raw text in, before parsing anything out of it.

```
Total Log Entries: 500
```

**Level 2 — Parse entries.** Turn one raw line into structured fields:
```
192.168.1.15 - POST /login 401
```
becomes
```
IP: 192.168.1.15
Method: POST
Endpoint: /login
Status: 401
```
Get this right on well-formed lines first — malformed-line handling comes later, don't solve both at once.

**Level 3 — Statistics.** Aggregate parsed entries into totals, status-code frequency, error counts, endpoint frequency, IP frequency. This is where maps stop being optional.

**Level 4 — Filtering and ranking.** Support queries like "show only errors," "show requests to /login," "show the top 5 endpoints." This is a separate concern from *computing* the statistics — don't let filtering logic leak into the statistics engine.

**Level 5 — Robustness.** Handle invalid lines, missing fields, unknown status codes, empty files, large files, invalid filenames — without the whole program going down over one bad line.

```
go run . server.log
go run . -top 5 server.log
```
Possible flags: `-total`, `-status`, `-errors`, `-top`, `-endpoint`, `-ip` (exact CLI design is your team's call).

### Watch for
- A log file will have at least one malformed line eventually — real or not, plan for it from Level 2 onward, don't bolt it on at Level 5. What should happen to the *rest* of the file when one line doesn't parse?
- "Most requested endpoint" requires deciding what happens on a tie — pick a rule as a team before it comes up in testing, not after.
- Statistics and filtering look similar (both "do something with the parsed entries") but are different jobs: one *computes* aggregate numbers, the other *selects* a subset. Keeping them separate modules, per your team division below, is not optional — it's what makes Level 4 not require touching Level 3's code.

### Team division

| Role | Owns | Hands off |
|---|---|---|
| **File Reader & Parser** | Reading the log file, splitting/parsing lines, extracting fields, flagging malformed entries | A list of structured, parsed entries (plus a count of skipped/malformed ones) |
| **Statistics Engine** | Total requests, status-code stats, error counts, endpoint stats, IP stats | Aggregate numbers, computed from the parsed entries |
| **Filtering, Search & Ranking** | Filter by status/endpoint/IP, top-N endpoints, sorting | A filtered/ranked subset of entries or stats, on request |
| **CLI & Reporting** | Command-line arguments, user-facing commands, error messages, report formatting, help menu, integration testing | The finished tool |

**Before any code is shared:** File Reader & Parser and Statistics Engine should agree on paper what a "parsed entry" looks like — what fields, what type for status code (string or int?), how a malformed line is represented (skipped silently, or passed through with an error flag?). That last question in particular determines how Level 5 gets built later — decide it now, not retroactively.

### Stuck? Ask better (team edition)
If a stat looks wrong, don't say "the counts are off." State: the exact log lines involved (or a minimal 2–3 line file that reproduces it), what count you expected, what you got, and whether the raw parsed entries (before aggregation) already look wrong — that tells you immediately whether the bug is in parsing or in the statistics/filtering logic layered on top.

### Mentor checkpoint questions
- What does a "parsed entry" look like in your data model, and who decided that shape?
- What happens, end to end, when your program hits a malformed line — where is that decision made, and by which module?
- How does filtering interact with statistics — are they computed from the same data, or separately?
- What's the largest log file you tested with, and did performance hold up?
- Could you add a new filter option live, without AI or a copied solution?

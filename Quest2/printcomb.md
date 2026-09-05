## printcomb

### Before you start
In your own words: what makes a combination "valid" here, and what makes it "unique"? Write both rules down before coding — this exercise has two separate constraints, not one.

### What to build
Print, in ascending order on one line, every combination of three *different* digits where the first < second < third. Separate combinations with `, `.

**Usage:**
```console
$ go run . | cat -e
012, 013, 014, 015, 016, 017, 018, 019, 023, ..., 689, 789$
$
```

- `000` / `999` are invalid — digits must differ.
- `987` is invalid — order must be ascending.

### Watch for
Three nested things need to move together (first digit, second digit, third digit) — but not all combinations of three loops are valid, only the ascending ones. Do you filter after generating, or only generate the valid ones to begin with?

### Stuck? Ask better
Show your loop structure and one example of a wrong combination it's producing (or a valid one it's missing) — that tells us whether your loop bounds or your ordering condition is off.

### Hints
<details><summary>Hint 1</summary>
Three nested loops, one per digit position — but each loop's starting point depends on the loop above it.
</details>
<details><summary>Hint 2</summary>
If digit 1 is `i`, digit 2 should start from `i+1`, and digit 3 should start from digit-2's value `+1`. That alone guarantees ascending order and no repeats — no extra filtering needed.
</details>

### Notions
- [01-edu/z01](https://github.com/01-edu/z01)

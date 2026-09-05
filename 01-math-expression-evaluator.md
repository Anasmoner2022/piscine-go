## Project — Math Expression Evaluator

**Team size:** 4
**Type:** CLI application, Go

---

### Before you start (as a team)

Before anyone writes code, sit together and answer this out loud: *in your own words, what does this program actually have to do, end to end?* Don't move on until all four of you can restate it the same way — this is the single biggest predictor of whether your modules will fit together later.

Then write down, as a team, one sentence per person: "I am responsible for ___, and I hand off ___ to ___." That sentence is your integration contract. Revisit it if it stops being true.

### Objective

Build a command-line calculator that receives a mathematical expression as a string and returns the correct result — respecting operator precedence and parentheses, the way a real calculator (or a real parser) would.

```
Input:  3 + 4 * 2
Output: 11        (not 14 — multiplication happens first)
```

### Core requirements

The program must:
- Accept a mathematical expression from the user
- Support `+`, `-`, `*`, `/`
- Ignore unnecessary spaces
- Respect operator precedence (`*`/`/` before `+`/`-`)
- Support parentheses, including nested parentheses
- Detect and reject: invalid expressions, missing operands, invalid operators, unmatched parentheses, division by zero
- Show meaningful error messages instead of crashing

```
Enter expression:
3 + 4 * 2 - (1 + 1)

Result:
9
```

### Build it in levels — don't jump to Level 5

**Level 1 — Basic calculator.** `3 + 4`, `10 - 3`, `5 * 6`, `20 / 4`. No precedence logic yet, just single-operator expressions.

**Level 2 — Operator precedence.** `2 + 3 * 4` must give `14`, not `20`. This is where you start thinking about *how* a program decides what to compute first — not just *what* the answer is.

**Level 3 — Parentheses.** `(2 + 3) * 4`, `10 / (2 + 3)`.

**Level 4 — Nested parentheses.** `3 * (2 + (4 * 5))`. This level is usually where teams realize a simple left-to-right pass isn't enough anymore.

**Level 5 — Validation and robustness.** Reject `3 +`, `* 5`, `3 + * 4`, `(3 + 4`, `10 / 0` — with a real error message, not a crash.

### Watch for
- Getting Level 2 right by accident (hardcoding "check for `*` first") won't survive Level 4. If your Level 2 solution can't explain *why* it handles precedence, it'll need to be rebuilt at Level 4 anyway — better to notice that now than after two more levels of work on top of it.
- Level 5 isn't an afterthought — a calculator that silently gives `0` or crashes on bad input is not "done," even if Levels 1–4 all pass.

### Team division

This project splits naturally into four handoffs — treat each as a pipeline, not four separate programs:

| Role | Owns | Hands off to next stage |
|---|---|---|
| **Tokenizer** | Reading the raw string, stripping spaces, identifying numbers/operators/parentheses | A clean list of tokens |
| **Parser** | Turning tokens into the right evaluation order — precedence, parentheses, nesting | A structure representing "what to compute in what order" |
| **Evaluator** | Doing the actual arithmetic in that order, including division-by-zero detection | A final numeric result (or an error) |
| **CLI / Validation** | User input/output, invalid-expression detection, error messages, test cases, gluing the other three together | The finished program |

**Before any code is shared:** the Tokenizer and Parser owners should agree on paper what a "token" looks like (what fields does it have?) — that's the actual contract, and disagreeing about it after both have written code is expensive. Same for Parser → Evaluator: agree on what structure represents "evaluation order" before either side builds against it.

### Stuck? Ask better (team edition)
When a teammate's module doesn't work with yours, "it's broken" isn't information. State: what you're passing across the boundary (exact input), what you expect back, what you're actually getting back, and which of the two modules you've each already checked. Most integration bugs at this stage are a mismatch in what each side *assumed* about the handoff — not a bug hiding inside one module.

### Mentor checkpoint questions
Each student should be able to answer, about their **own** part:
- What input does your module receive, and what does it return?
- What happens if the input is malformed — does your module detect that, or pass the problem downstream?
- What's the trickiest edge case in your part, and how did you find it?
- Can you explain the full flow from raw string to final result, including parts you didn't write?
- Could you modify your module without AI or a copied solution, right now, live?

That last question matters more than whether the demo works.

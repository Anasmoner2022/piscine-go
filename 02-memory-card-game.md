## Project — Memory Card Game

**Team size:** 4
**Type:** Console application, Go

---

### Before you start (as a team)

Restate the goal out loud, all four of you, the same way: *what does "the game" actually consist of — a board, a state, a loop, and what else?* This project has more moving state than Project 1 did (hidden/revealed/matched, per card, changing every turn) — if you don't agree on what "the state" is before splitting up, you'll each build a different mental model of it.

Write your integration contract: one sentence per person, "I own ___, I hand off ___ to ___."

### Objective

A console game where the player flips two cards at a time from a hidden board, trying to find matching pairs. Matches stay revealed; non-matches flip back. The game ends when every pair is found.

No web, HTTP, HTML/CSS, or concurrency needed — this is a console app, and the challenge is entirely in state management, not infrastructure.

```
Welcome to Memory Card Game!
Enter your name:
Sohila
```

### Core requirements

- Generate pairs of cards and shuffle them onto a board
- Track three states per card: **hidden**, **revealed**, **matched**
- Let the player pick two cards; compare them; keep matches visible, hide non-matches again
- Track attempts, successful matches, pairs remaining, and score
- Support three difficulty levels with different board sizes
- Validate all player input
- Detect the win condition and show a final summary
- Offer play-again / exit after a win

### Build it in levels

**Level 1 — Board & state, Easy only.** Get a 4×4 board (8 pairs) generating, shuffling, and displaying correctly with all cards hidden. No game logic yet — just prove the board is right.

**Level 2 — Core game loop.** Player selects two cards, they compare, matches stay revealed, non-matches flip back after a moment. This is the heart of the project — get this rock solid on the small board before scaling up.

**Level 3 — Levels, attempts, score.** Add Medium (6×6, 18 pairs) and Hard (8×8, 32 pairs). Add attempt counting, match counting, and a scoring rule your team agrees on and can explain.

**Level 4 — Validation & polish.** Reject out-of-range positions, re-selecting an already-matched card, selecting the same card twice, and non-numeric input — each with a real message, not a crash. Add the win screen and play-again loop.

```
Player: Ahmed
Level: Hard
Attempts: 42
Pairs Found: 32/32
Score: 280

You completed the game!
1. Play Again
2. Exit
```

### Watch for
- The three card states (hidden / revealed / matched) are easy to collapse into a single boolean by accident ("is it shown or not?") — but "matched" and "temporarily revealed" behave differently on the next turn. If your Level 1 board only tracks true/false, Level 2 will force a rewrite.
- Scaling from 4×4 to 8×8 (Level 3) should be a config change, not a rewrite. If it isn't, that's a sign the board size got hardcoded somewhere in Level 1 or 2.
- "The cards flip back" implies a *pause* the player can see before they're hidden again — don't compare and hide in the same instant, or the player never actually gets to see what they picked.

### Team division

| Role | Owns | Hands off |
|---|---|---|
| **Board & Cards** | Generating pairs, building the board, shuffling, displaying it, tracking card positions | A board structure the rest of the team can query and update |
| **Game Logic** | Selecting two cards, comparing them, updating hidden/revealed/matched state, detecting the win condition | Turn results (match or no match) to the scoring layer |
| **Levels, Attempts & Score** | Easy/Medium/Hard board sizing, attempt counting, score calculation, pairs-remaining tracking | Current stats, on demand, to the CLI layer |
| **CLI, Validation & Integration** | Player name, difficulty menu, input validation, play-again loop, error messages, wiring the other three together | The finished game |

**Before any code is shared:** Board & Cards and Game Logic should agree on paper what a "card" is (what fields — value, state, position?) and what a "board" exposes (can Game Logic ask for a card by position? does it get a reference or a copy?). That agreement is the actual interface — get it wrong and every downstream module inherits the mismatch.

### Stuck? Ask better (team edition)
If a turn produces the wrong result, don't say "the matching is broken." State: the two positions selected, what state each card was in *before* the turn, what state your teammate's module says they ended up in *after*, and whether the bug reproduces on a fresh 4×4 board or only at larger sizes. That last detail alone often tells you whether it's a logic bug (small board too) or a scaling bug (only at 6×6/8×8).

### Mentor checkpoint questions
- What are the three card states in your data model, and what triggers each transition?
- How does your module know the game is won — what condition are you checking?
- What happens if the player selects the same position twice in a row?
- Walk through one full turn, from player input to updated board, across all four modules.
- Could you change the board size handling live, without AI or a copied solution?

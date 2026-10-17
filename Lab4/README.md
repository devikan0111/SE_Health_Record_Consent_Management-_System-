# Lab 4: Vibe Coding with an LLM (Blackjack)

A terminal Blackjack vs Dealer game in Python. The broken code was fixed and the
missing features were added one task at a time, using an LLM as a coding
assistant.

**Code repo (with a separate commit for each task):**
https://github.com/devikan0111/SE_18_blackjack

## Contents

| File | Description |
| --- | --- |
| `before.mp4` | Video of the original game before any changes |
| `after.mp4` | Video of the final game after all changes |
| `main.py`, `game.py`, `cards.py`, `requirements.txt` | Updated code |
| `Lab4_chat_history.pdf` | Exported chat history with the prompts and explanations |

## The bug that was fixed

The original `hand_value()` in `cards.py` always counted an Ace as 11. The hand
`JC 2C AH` was shown as 23 and counted as a bust, when the correct total is 13.
The before video shows this.

## Tasks

| Task | What changed | File |
| --- | --- | --- |
| 1. Fix Ace scoring | Aces count as 11 and drop to 1 when needed to avoid a bust | `cards.py` |
| 2. Round resolution | Natural blackjack, player bust, dealer bust, dealer draws to 17, ties, and the round ends cleanly | `game.py` |
| 3. Chips and betting | Validated bets, chips carry over between rounds, blackjack pays 3:2 (rounded down for odd bets), game over at 0 chips | `game.py` |
| 4. Feedback and robustness | Messages for every card drawn, validated "Play again?", `q` quits from any prompt, safe handling of an empty deck | `game.py` |

## Before and after

- **Before:** no betting, chips never shown, Aces always worth 11, and a bust
  printed only "Bust." with no chip result.
- **After:** bets are validated, chips are shown at the start and end of each
  round, each draw prints the card and the new total, Aces count as 1 when
  needed, and invalid input never changes the chips.

## How to run

```
python main.py
```

Use `h` to hit, `s` to stand and `q` to quit.

## Notes

- The lab was done in the Blackjack repo linked above. The commits there show
  each task separately: Task 1 (Ace scoring), Task 2 (round resolution),
  Task 3 (chips and betting) and Task 4 (feedback and robustness).
- Chat history was exported from the LLM and is included as a PDF.

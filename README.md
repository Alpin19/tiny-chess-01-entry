# tiny-chess-01-entry

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Alpin19/tiny-chess-01-entry/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Alpin19/tiny-chess-01-entry/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An original 0x88 negamax chess engine: alpha-beta search with principal-variation search, null-move pruning and late-move reductions, quiescence search with check replies, a transposition table with killer-move ordering, and material plus piece-square evaluation with bishop-pair and endgame king terms. It plays on a fixed 80,000-node budget per move — no clock, no randomness — so every game is fully deterministic, and the whole engine packs into 4 KB of Python.

## Revision note (revert to the known-good build)

The first submission of this entry was rejected: the server's practice grade was 997, below the 1,154 floor. Local diagnosis reproduced the weakness deterministically on practice trial-0 — the submitted build scored 1W/1D/4L, while the pre-revision build scored 4W/0D/2L in two identical runs. The two revisions made after the original build (deeper late-move reductions, and a rank-scaled passed-pawn evaluation bonus) weakened the engine, so this commit restores the exact pre-revision engine byte-for-byte. Perft still passes 14/14 on the packed entrypoint.

## Run it

```sh
MAKEFUN_ENV_URL=<env-url> python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=8qvktrba&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>

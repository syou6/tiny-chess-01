# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/syou6/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/syou6/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4,096 bytes of Python. `main.py` is the whole
engine, shipped as a self-unpacking lzma payload (the rules allow a
compressed payload with its unpacker): a 0x88 board with piece-square
values baked into the pieces, an incremental score, negamax alpha-beta
with PVS, a Zobrist transposition table, quiescence search with delta
pruning, MVV-LVA / killer / TT-move ordering, repetition-aware draw
scoring, and iterative deepening under a fixed node budget — never a
clock, so every replay plays the same moves. It plays the make.fun
gauntlet through the env at `MAKEFUN_ENV_URL` (POST /game, /move),
one game after another.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:18700 python3 main.py
```

Python 3.13, standard library only. Point `MAKEFUN_ENV_URL` at a running
competition env (the kit's `program/env/server.mjs`); the engine asks for
the game in play and answers with UCI moves until the env reports done.

---

Entered on [make.fun](https://make.fun/?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards

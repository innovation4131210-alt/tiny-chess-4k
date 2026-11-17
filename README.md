# tiny-chess-01 — a chess engine in 4 KB of Python

[![make.fun tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/c/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/__OWNER__/__REPO__/rank.svg)](https://make.fun/c/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/__OWNER__/__REPO__/reward.svg)](https://make.fun/c/tiny-chess-01)

An entry to [make.fun's tiny-chess-01](https://make.fun/c/tiny-chess-01):
the strongest chess engine that fits in 4,096 bytes of Python.

`main.py` (4,014 bytes) is the whole engine: an LZMA-packed source that
unpacks and execs itself. It plays every game through the env at
`MAKEFUN_ENV_URL` and searches to a fixed node budget — never a clock —
so its moves replay exactly.

Inside: a 0x88 board, negamax alpha-beta with PVS and LMR, check
extensions, a transposition table, quiescence search, and tapered
material + piece-square-table evaluation (classic published tables,
letter-encoded to fit). No model is called; Python 3.13 standard
library only.

The readable source lives outside the committed tree; `main.py` is
generated from it with the kit's `makefun compress`.

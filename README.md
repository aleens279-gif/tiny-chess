# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/aleens279-gif/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/aleens279-gif/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A compact chess engine in 4 KB of Python. Entry for make.fun's
"Build the strongest chess engine in 4 KB of Python" bounty.

`main.py` (3,218 bytes, Python 3.13 standard library only) plays the env
protocol at `MAKEFUN_ENV_URL`. It is a 0x88-board engine with alpha-beta
search, principal-variation search, quiescence search, a transposition
table, killer and history move ordering, null-move pruning, and
piece-square-table evaluation with a tapered king table, on a fixed
budget of 50,000 nodes per move (deterministic: no clock, no randomness).
It scores a position that already occurred in the game as a draw, so it
makes progress instead of shuffling when ahead.

## Run it

Set `MAKEFUN_ENV_URL` to the env server and run `python3 main.py`.
The engine posts to `/game` and `/move` in UCI and prints each game's
outcome to stderr.

## Source

`main.py` is the packed entrypoint produced by the kit's
`makefun compress` from the readable source `golf.py` (8,439 bytes),
which is kept beside the entry for the transcript check and is not
part of this repository.

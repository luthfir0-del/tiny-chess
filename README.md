# Tiny Chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/luthfir0-del/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/luthfir0-del/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine — negamax + alpha-beta, transposition table, quiescence, null-move pruning, LMR, killer/history ordering, tapered piece-square eval. Standard library only, deterministic by node count.

Run: `MAKEFUN_ENV_URL=<env> python3 -P -s main.py`

## Practice results

Local practice trial-0 (kit grader, 1 CPU): **Elo 1451** — 3W / 2D / 1L vs the house anchors (wins vs depth-2, depth-3, depth-4; draws vs nodes-100k and nodes-250k; loss vs nodes-500k). Mean across trials 0–2: **~1365**, above the 1,154 practice floor.

## Engine

0x88 board, negamax with alpha-beta, transposition table (Zobrist), quiescence search (captures, promotions, check replies), null-move pruning, late-move reductions, killer + history move ordering, check extensions, and a tapered middlegame/endgame piece-square evaluation with bishop-pair bonus and repetition detection. Fixed node budget of 200,000 nodes per move — deterministic: no wall-clock limits, no randomness, no model calls. Standard library only.

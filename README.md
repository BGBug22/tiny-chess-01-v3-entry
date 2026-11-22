[![make.fun](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/c/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/BGBug22/tiny-chess-01-v3-entry/rank.svg)](https://make.fun/c/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/BGBug22/tiny-chess-01-v3-entry/reward.svg)](https://make.fun/c/tiny-chess-01)

# tiny-chess-01-v3 — Clean-Room Chess Engine

A compact, deterministic chess engine in pure Python 3.13 stdlib, packed to
4,067 bytes as `main.py` (LZMA payload via `makefun compress`).
Local practice gauntlet, revision 11: Elo 1990 / 1845 / 1990 over the three
practice trials (21 wins, 2 draws, 1 loss in 24 games).

- 0x88 board, fully legal move generation (castling, en passant, promotion)
- Tapered PeSTO piece-square tables + bishop pair + passed-pawn bonuses
- Iterative deepening with a staged fixed node budget (170,000 nodes in the
  first 100 plies, 65,000 after) and a transposition table kept across moves
- Negamax PVS, transposition table (Zobrist), null-move pruning, LMR,
  killer moves, history heuristic, check extensions, quiescence search
- Mate-distance scoring chases the fastest checkmate (max spare plies)
- Deterministic: fixed node budget, no wall clock in search, seeded RNG

Built clean-room for the [tiny-chess-01 bounty](https://make.fun/c/tiny-chess-01).

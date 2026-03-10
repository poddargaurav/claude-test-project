# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
A single-file browser-based Tic Tac Toe game. No build tools, frameworks, or dependencies.

## Running the Game
Open `tictactoe.html` directly in any browser:
- Windows: `start tictactoe.html`
- Or double-click the file in Explorer

## Architecture
Everything lives in `tictactoe.html` — HTML structure, CSS styles, and JavaScript logic are all inline in one file.

**Key JavaScript components:**
- `play(i)` — handles a cell click; delegates to AI if in AI mode
- `mark(i, player)` — places a marker and switches the current player
- `aiMove()` — triggers the AI with a 300ms delay
- `minimax(board, player)` — recursive minimax returning the best move index and score
- `checkWin()` / `getWinner(board)` — checks the 8 win combinations in `WINS`
- `endGame(winner, combo)` — finalizes the game, highlights winning cells, updates scores
- `resetBoard()` — clears board state for a new round (scores persist)
- `setMode(m)` — switches between `'pvp'` and `'ai'` modes and resets the board

**State variables:** `board` (9-element array), `current` ('X'|'O'), `over` (bool), `mode` ('pvp'|'ai'), `scores` ({X, O, Draw})

## Git Workflow
Commit and push to GitHub regularly throughout any work session so progress is never lost.

- Commit after each meaningful change (feature added, bug fixed, refactor done)
- Use clear, descriptive commit messages in imperative mood (e.g. `Add draw detection logic`, `Fix minimax scoring bug`)
- Push to the remote after every commit: `git add -A && git commit -m "message" && git push`
- Never leave a session with uncommitted or unpushed work

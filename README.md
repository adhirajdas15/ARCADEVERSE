# ARCADEVERSE
**50 Games. 100 Levels. Infinite Fun.**

A GitHub-ready specification and development scaffold for a browser arcade platform containing 50 distinct games.

## Upload to GitHub
1. Create a new GitHub repository named `arcadeverse`.
2. Upload this folder's files to the repository (or upload the ZIP and extract it locally first).
3. Open the repository in GitHub Copilot coding agent / your coding environment.
4. Start with the instructions in `BUILD_PLAN.md`. Work in phases; do not ask the agent to implement all 50 games in one pass.

## Product requirements
- 50 distinct playable games (catalog in `games.json`).
- At least 100 meaningful levels for each game.
- Independent score, high score, previous score, session history and level progress per game.
- Automatic persistent saves; offline-friendly storage; optional cloud sync later.
- Responsive controls: keyboard, mouse and touch where appropriate.
- Pause, resume, restart, mute, exit, achievements and game-over screen.
- No placeholder or inert games in the final product.

## Suggested technology
React + TypeScript + Vite, HTML Canvas for action games, CSS for UI, IndexedDB for persistent records (use a storage adapter so cloud sync can later be added).

## Logo
`logo.png` is the generated ARCADEVERSE concept logo. Treat it as a visual reference; create scalable SVG/app icon versions during the implementation phase.

## Development checklist
Use `BUILD_PLAN.md` and `games.json` as the source of truth. Update the checklist as each game is implemented, tested and verified.

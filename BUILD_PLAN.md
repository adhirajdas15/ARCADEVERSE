# ARCADEVERSE — GitHub Agent Build Instructions

## Agent rules
- Build a genuinely playable application, not a static mockup.
- Work phase-by-phase; run the app, tests, typecheck and build after each phase.
- Never mark a game complete unless its gameplay, controls, scoring, levels, persistence, restart/pause and game-over flows are implemented and tested.
- Use a shared game contract, but keep each game's mechanics unique.
- Create 100+ level definitions or deterministic level-generation rules per game with meaningful difficulty changes. Avoid simply changing a level number.
- Persist data using IndexedDB, with migrations/versioning and robust error handling. Do not rely on volatile React state. LocalStorage may be used only for small preferences.
- Save each session's score, date, duration, level reached, outcome and game slug. Preserve personal bests; never overwrite a best with a lower score.
- When a game is opened, show previous score, personal best, current/unlocked level and recent sessions.
- Keyboard, touch and mouse inputs must be supported where sensible; provide accessible labels and focus states.
- Prevent game loops from running while paused, the tab is hidden, or the game is disposed. Clean up listeners and timers.
- Add unit tests for game rules and storage; add browser tests for the catalog and representative gameplay.
- Do not use copyrighted game art, sprites, music or trademarked characters. Create original visual designs inspired only by broad genres/mechanics.

## Phases

### Phase 1 — Platform foundation
Create Vite + React + TypeScript app, responsive neon UI, navigation, catalog, search, category filters, favorites, dashboard, profile/statistics, history, achievements, settings, reusable game shell, storage layer and tests. Provide working catalog cards and a clear implementation status (not falsely marked playable).

### Phase 2 — Games 1–10: classic arcade
Implement Snake, Tetris, Maze Chaser (original maze mechanics), Brick Breaker, Pong, Space Invaders-style original shooter, Flappy-style flight, Frogger-style crossing, Whack-a-Mole, Climb Platformer. Each game must have 100 levels, scoring, saves, last score and personal best.

### Phase 3 — Games 11–20: space/shooting
Galaxy Shooter, Asteroid Smash, Space Survival, Alien Defense, Meteor Dodge, Star Fighter, UFO Hunter, Space Rescue, Laser Arena, Boss Battle.

### Phase 4 — Games 21–27: racing
Highway Racer, Formula Racing, Drift Challenge, Mini Kart Racing, Motorcycle Racer, Traffic Racer, Monster Truck Challenge.

### Phase 5 — Games 28–37: puzzle/brain
2048, Sudoku, Minesweeper, Match-3, Sliding Puzzle, Memory Cards, Word Guess, Word Scramble, Chess, Checkers.

### Phase 6 — Games 38–45: competitive/casual
Tic-Tac-Toe, Rock Paper Scissors, Simon Says, Reaction Speed, Basketball Shots, Penalty Shootout, Target Archery, Bowling.

### Phase 7 — Games 46–50: adventure/other
Mini Platform Adventure, Treasure Hunt, Endless Runner, Zombie Survival (stylized, non-graphic), Tower Defense.

### Phase 8 — Quality assurance
Audit all 50 games against `games.json`; verify 100+ levels, unique gameplay, score and previous score, persistence, controls, pause/resume/restart, mobile layout and tests. Fix all issues before reporting completion.

## Required shared game interface
Define a typed game manifest and game host contract including: slug, title, category, description, input capabilities, level count, mount/dispose, pause/resume, restart, current score, level, completion/failure and rendering/update. Adapt this contract as needed, but keep module boundaries clear.

## Score/history model
Store records per player and per game:
- personalBest
- previousScore
- currentLevel
- unlockedLevel
- completedLevels
- totalSessions
- totalPlayTime
- recentSessions (bounded, e.g. latest 100)

Each session: session ID, game slug, started/ended timestamps, duration, score, level reached, result, and optional metadata. Use transactional updates so a session save cannot corrupt progress.

## Completion reporting
At each phase, report exactly which games are playable, which features are tested, any known limitations and commands to run. Do not claim unimplemented work is done.

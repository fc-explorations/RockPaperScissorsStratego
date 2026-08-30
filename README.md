# Rock Paper Scissors Stratego

Play the live game: **[fc-explorations.github.io/RockPaperScissorsStratego](https://fc-explorations.github.io/RockPaperScissorsStratego/)**

Rock Paper Scissors Stratego is a local two-player, pass-and-play strategy game inspired by Stratego. You can play against another person or choose **Play vs computer** to let the computer control Player 2. Each player starts with a random army of Rock, Paper, Scissors, and one Flag, then tries to capture the opponent's Flag without exposing their own formation.

## Play locally

No build step or dependencies are required.

1. Clone the repository:

   ```bash
   git clone https://github.com/fc-explorations/RockPaperScissorsStratego.git
   cd RockPaperScissorsStratego
   ```

2. Open `index.html` directly in a browser, or serve the folder with any static web server.

## How to play

1. Choose **Pass & play** or **Play vs computer**.
2. Both armies are placed randomly in their home rows, including a random extra Rock, Paper, or Scissors. Each Flag starts protected on the back line.
3. Before the opening move, select two friendly pieces in succession to swap them. Select a piece and an empty adjacent square to make the opening move and start the game.
4. Players alternate turns. Every piece moves one square horizontally or vertically. Flags can move but cannot attack.
5. Moving a non-Flag piece onto an enemy piece starts combat:
   - Rock defeats Scissors.
   - Scissors defeats Paper.
   - Paper defeats Rock.
   - Matching pieces become rubble, and that cell is forbidden for the rest of the game.
   - Any mobile piece captures the Flag.
   - A player with only their Flag remaining loses immediately.
6. Capture the opposing Flag to win.

Enemy pieces remain hidden until combat reveals them. A revealed enemy that survives remains known for the rest of the game.

## Controls

- Click or tap a piece to select it.
- Click or tap a highlighted square to move or attack.
- Before the opening move, tap two friendly pieces in succession to swap them, or move a piece to an empty adjacent square to start the game.
- Use **Rules** to review the rules and **New game** to restart.

In computer mode, Player 2's random formation stays hidden and takes a brief pause before each move. Battles resolve directly on the main board: both combatants are revealed, animated, and resolved automatically. The computer uses a lightweight strategy that prioritizes attacks, winning attacks, Flag threats, and forward movement. It will take a chance on hidden enemy pieces rather than always walking past them.

## Project structure

```text
.
├── index.html          # Complete game: HTML, CSS, and JavaScript
└── assets/             # Generated Rock, Paper, Scissors, and Flag artwork
```

The project is intentionally self-contained and uses no backend, npm packages, external libraries, or external assets.

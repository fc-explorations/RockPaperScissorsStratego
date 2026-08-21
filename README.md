# Rock Paper Scissors Stratego

Play the live game: **[fc-explorations.github.io/RockPaperScissorsStratego](https://fc-explorations.github.io/RockPaperScissorsStratego/)**

Rock Paper Scissors Stratego is a local two-player, pass-and-play strategy game inspired by Stratego. Each player secretly deploys an army of Rock, Paper, Scissors, and one Flag, then tries to capture the opponent's Flag without exposing their own formation.

## Play locally

No build step or dependencies are required.

1. Clone the repository:

   ```bash
   git clone https://github.com/fc-explorations/RockPaperScissorsStratego.git
   cd RockPaperScissorsStratego
   ```

2. Open `index.html` directly in a browser, or serve the folder with any static web server.

## How to play

1. Player 1 chooses a secret extra Rock, Paper, or Scissors and deploys all eight pieces in the bottom two rows.
2. Pass the device to Player 2, who privately chooses their extra piece and deploys their army.
3. Players alternate turns. Rock, Paper, and Scissors move one square horizontally or vertically. The Flag cannot move.
4. Moving onto an enemy piece starts combat:
   - Rock defeats Scissors.
   - Scissors defeats Paper.
   - Paper defeats Rock.
   - Matching pieces eliminate each other.
   - Any mobile piece captures the Flag.
5. Capture the opposing Flag to win.

Enemy pieces remain hidden until combat reveals them. A revealed enemy that survives remains known for the rest of the game.

## Controls

- Click or tap a piece to select it.
- Click or tap a highlighted square to move or attack.
- During deployment, use the tray to place pieces and use **Randomize**, **Reset**, or piece swapping to arrange your formation.
- Use **Rules** to review the rules and **New game** to restart.

## Project structure

```text
.
├── index.html          # Complete game: HTML, CSS, and JavaScript
└── assets/             # Generated Rock, Paper, Scissors, and Flag artwork
```

The project is intentionally self-contained and uses no backend, npm packages, external libraries, or external assets.

# Rock Paper Scissors Stratego

Play the live game: **[fc-explorations.github.io/RockPaperScissorsStratego](https://fc-explorations.github.io/RockPaperScissorsStratego/)**

Rock Paper Scissors Stratego is a local two-player, pass-and-play strategy game inspired by Stratego. You can play against another person or choose **Play vs computer** to let the computer control Player 2. Each player secretly deploys an army of Rock, Paper, Scissors, and one Flag, then tries to capture the opponent's Flag without exposing their own formation.

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
2. Player 1 chooses a secret extra Rock, Paper, or Scissors and deploys all eight pieces in the bottom two rows.
3. In pass-and-play, pass the device to Player 2, who privately chooses their extra piece and deploys their army. In computer mode, Player 2 is deployed automatically in private.
4. Players alternate turns. Rock, Paper, and Scissors move one square horizontally or vertically. The Flag cannot move.
5. Moving onto an enemy piece starts combat:
   - Rock defeats Scissors.
   - Scissors defeats Paper.
   - Paper defeats Rock.
   - Matching pieces eliminate each other.
   - Any mobile piece captures the Flag.
   - A player with only their Flag remaining loses immediately.
6. Capture the opposing Flag to win.

Enemy pieces remain hidden until combat reveals them. A revealed enemy that survives remains known for the rest of the game.

## Controls

- Click or tap a piece to select it.
- Click or tap a highlighted square to move or attack.
- During deployment, tap empty home squares to place the next piece in order. You can still use the tray for swapping, plus **Randomize** and **Reset** to arrange your formation.
- Use **Rules** to review the rules and **New game** to restart.

In computer mode, Player 2 deploys privately and shows a short thinking screen before each move. The computer uses a lightweight strategy that prioritizes winning attacks, Flag threats, and forward movement.

## Project structure

```text
.
├── index.html          # Complete game: HTML, CSS, and JavaScript
└── assets/             # Generated Rock, Paper, Scissors, and Flag artwork
```

The project is intentionally self-contained and uses no backend, npm packages, external libraries, or external assets.

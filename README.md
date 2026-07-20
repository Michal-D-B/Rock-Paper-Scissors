# Rock, Paper, Scissors 🪨 📄 ✂️

A command-line Rock, Paper, Scissors game written in Python. Play best-of-three rounds against the computer, see a formatted scoreboard, and rematch as many times as you like.

## Features

- **Play against the computer** — the computer picks its move at random each round.
- **Three rounds per game** — scores are tallied across all three before a winner is declared.
- **Input validation** — the game keeps asking until you type a valid move, so typos and stray spaces won't crash it.
- **Rematch loop** — after each game you choose whether to play again.
- **Formatted scoreboard** — results are displayed in a clean, aligned table.
- **Friendly fallback** — forget to enter a name? You'll be greeted as "Silent Ninja".

## How to Play

1. Run the program.
2. Enter your name when prompted.
3. Each round, type your choice: `rock`, `paper`, or `scissors`.
4. The computer reveals its move and the round result (Win, Lose, or Draw) is shown.
5. After three rounds, the final scoreboard appears.
6. Choose `yes` to rematch or `no` to quit.

## Requirements

- Python 3.x

No external libraries are needed — the game uses only Python's built-in `random` module.

## Running the Game

Clone the repository and run the script:

```bash
python rock_paper_scissors.py
```

Or, if you're using the Jupyter notebook version, open `Rock Paper Scissors.ipynb` and run the cell.

## How It Works

The program is organised into small, single-purpose functions:

| Function | Responsibility |
|----------|---------------|
| `main()` | Runs the overall flow: rules, name, game loop, and rematch. |
| `rules()` | Prints the welcome banner and instructions. |
| `name()` | Asks for the player's name (with a fallback if none is given). |
| `game(n, words)` | Plays `n` rounds and returns the computer and player scores. |
| `user_input(words)` | Gets and validates the player's move. |
| `end_score(...)` | Displays the final scoreboard. |
| `end_game(name)` | Asks whether the player wants a rematch. |

The winning logic uses a dictionary that maps each move to the move it beats:

```python
{
    "paper": "rock",
    "rock": "scissors",
    "scissors": "paper"
}
```

If the player's move maps to the computer's move, the player wins the round — a compact alternative to a long chain of `if` statements.

## Possible Improvements

Some ideas for extending the game:

- Let the player choose the number of rounds.
- Add a running score across multiple games.
- Expand to Rock, Paper, Scissors, Lizard, Spock.
- Add coloured terminal output.

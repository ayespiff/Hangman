# Hangman

A command-line Hangman game in Python with three difficulty levels, input validation and session statistics. Built for the Rockborne Python module.

## How to Run

Requires Python 3.8 or newer. No external packages are needed.

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
python hangman.py
```

You can also open the notebook in VS Code or Jupyter and choose **Run All**.

## How to Play

1. Choose a difficulty: `1` easy (3-letter words), `2` medium (6 letters) or `3` hard (8 to 10 letters).
2. Guess one letter at a time. Correct letters are revealed in the word.
3. Each wrong guess costs one of your 6 lives and adds to the gallows.
4. Reveal the whole word to win. Lose all 6 lives and the word is revealed.
5. After each game your stats are shown and you can play again (`y`) or quit (`n`).

Repeated guesses do not cost a life.

## Input Validation

Invalid input never crashes the game. The player is shown a message and asked again when they:

- choose a difficulty other than 1, 2 or 3
- enter nothing, more than one character, or a number or symbol
- guess a letter they have already tried
- answer "play again" with anything other than y or n

Pressing `Ctrl + C` exits cleanly.

## Statistics

Global counters track games played, won and lost, total guesses, current streak and best streak. The game also shows the win rate and average guesses per game. Stats reset when the program closes.

## Code Structure

| Function                 | Purpose                                                  |
|--------------------------|----------------------------------------------------------|
| `main()`                 | Runs the game loop and handles a clean exit              |
| `play_round()`           | Plays one full game from difficulty choice to win or loss |
| `choose_difficulty()`    | Gets a valid difficulty level                            |
| `get_valid_guess()`      | Gets a valid, new letter                                 |
| `play_again()`           | Gets a valid y or n answer                               |
| `update_stats()`         | Updates the global counters after each game              |
| `show_stats()`           | Displays the session statistics                          |
| `display_board()`        | Shows the gallows, masked word and lives left            |
| `mask_word()`            | Hides unguessed letters as underscores                   |
| `display_instructions()` | Shows the rules                                          |

Every function has a docstring and the code follows PEP 8. The game logic is planned in `pseudocode.md`.

## Files

- `hangman.py`: the game
- `Python_04_01_Project_PythonGameDevelopment.ipynb`: notebook version
- `README.md`: this file

## Future Improvements

A Tkinter graphical interface, stats saved to a file between sessions, and themed word categories.

## Author
Aye Spiff

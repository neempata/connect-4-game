# Connect 4 (Pygame)

A simple endless runner game built with Python and Pygame. The player controls a T-Rex that must jump over randomly generated obstacles while the game gradually becomes faster and more challenging.

A local two-player Connect 4 implementation built with Python and Pygame. Players take turns clicking a column to drop their colored piece into the board. The first player to connect four in a row (horizontal, vertical, or diagonal) wins.

## Project Overview

The game presents a 7×6 board (7 columns, 6 rows). Players alternate turns dropping pieces into columns by clicking the board. Pieces stack from the bottom up and disappear off-screen only when the window is closed or the game is reset after a win.

When a winning alignment is detected the game displays a winning message and pauses briefly before allowing a restart.

## Features

- Two-player local gameplay (alternating turns)
- Mouse-click column selection
- Accurate board and win-detection logic (horizontal, vertical, diagonal)
- Clean, colorful Pygame rendering with circle pieces
- Simple, single-file implementation (`connect4.py`) for easy experimentation
- Console board printout for debugging

## Technologies Used

- Python
- Pygame
- NumPy (for board representation)

## How the Game Works

### 1. Board and Pieces

The board is represented by a NumPy 2D array with `ROW_COUNT = 6` and `COLUMN_COUNT = 7`. Empty cells are `0`. Player 1 uses `1` (purple), Player 2 uses `2` (pink). The UI draws a stacked grid of circles representing each cell.

### 2. Player Input

Players select a column by clicking inside the game window. The code converts the mouse `x` position into a column index and drops the piece into the lowest available row in that column.

### 3. Turn Management

The `turn` variable alternates between `0` and `1`. After a valid drop the code checks for a winning move. If a win occurs the game shows a message and sets `game_over = True`.

### 4. Win Detection

The `winning_move(board, piece)` function scans the board for four connected pieces in all directions:
- Horizontal: left → right
- Vertical: top → bottom
- Positive-slope diagonal
- Negative-slope diagonal

If any check finds four in a row the function returns `True`.

### 5. Rendering

The Pygame window size is computed from the `SQUARESIZE`, `ROW_COUNT`, and `COLUMN_COUNT`. The top row is used for a floating preview circle that tracks the mouse and indicates the current player's drop position. The board squares are drawn in cyan with circle pieces in black (empty), purple (Player 1), and pink (Player 2).

## Controls

- Click a column: Drop your piece in that column
- Close window: Quit the game

## Requirements

- Python 3.x
- Pygame
- NumPy

## Installation

Clone or download the project and open a terminal inside the project folder.

Install dependencies:

```powershell
python -m pip install pygame numpy
```

## Running the Game

Run the main file:

```powershell
python connect4.py
```

The window opens immediately. Move your mouse to aim and click to drop a piece.

## Project Structure

```text
connect-4-game/
├── connect4.py   Main game file
├── README.md     Project documentation
```

## Game Loop

Start game
    |
    v
Read Pygame events (mouse, window)
    |
    v
Process input → validate column → drop piece
    |
    v
Check for a winning move
    |
    v
Draw board and UI
    |
    v
Repeat at frame rate until quit

## What I Learned

This project reinforced how grid-based games separate game logic (board state, win detection) from rendering (Pygame drawing). Working with a NumPy array made board checks concise and easy to reason about. Implementing mouse-based column selection highlighted the importance of coordinate transforms when mapping screen input to game state.

## Future Improvements

- Add a simple AI opponent (minimax or heuristic)
- Highlight the four pieces that form a winning line
- Add a restart button and on-screen controls
- Add sound effects and animations
- Add move-undo and move-history display
- Implement a single-player timed mode or difficulty levels

## Possible Challenges

### Pygame is not installed

If you see `ModuleNotFoundError: No module named 'pygame'`, run:

```powershell
python -m pip install pygame
```

### NumPy is not installed

If you see `ModuleNotFoundError: No module named 'numpy'`, run:

```powershell
python -m pip install numpy
```

### The window closes immediately

Run the game from a terminal to keep error messages visible:

```powershell
python connect4.py
```

## License

This project is open source and available for learning, practice, and modification.

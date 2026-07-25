# Connect 4 Game

A two-player Connect 4 game built with Python, Pygame, and NumPy. The game has a simple graphical interface, live piece previews, alternating player turns, and automatic win detection.

## Features

- Classic 6-row by 7-column Connect 4 board
- Local two-player gameplay
- Interactive mouse controls
- Live preview showing where the next piece will be placed
- Automatic horizontal, vertical, and diagonal win detection
- Color-coded players:
  - Player 1 uses purple pieces
  - Player 2 uses pink pieces
- Console output showing the board after every move

## Requirements

- Python 3
- Pygame
- NumPy

## Installation

1. Clone or download this repository.

2. Open a terminal in the project folder.

3. Install the required packages:

```bash
python -m pip install pygame numpy
```

## Usage

Run the game with:

```bash
python connect4.py
```

A new game window will open automatically.

## How to Play

1. Player 1 starts with the purple pieces.
2. Move the mouse across the top of the window to preview the current player's piece.
3. Click a column to drop the piece into the lowest available position.
4. Players continue taking turns.
5. The first player to connect four pieces horizontally, vertically, or diagonally wins.

If a column is full, clicking it will not place a piece.

## How It Works

### Board Setup

The game board is stored as a NumPy array with 6 rows and 7 columns. Empty spaces are represented by `0`, Player 1 pieces by `1`, and Player 2 pieces by `2`.

### Piece Placement

When a player clicks a column, the game checks whether that column has an open space. The piece is then placed in the lowest available row.

### Win Detection

After every valid move, the game checks for four matching pieces in:

- Horizontal lines
- Vertical lines
- Positively sloped diagonals
- Negatively sloped diagonals

### Game Display

Pygame handles the game window, mouse input, board drawing, piece colors, and title text. NumPy manages the board data and makes it easy to track each position.

## Project Structure

```text
.
|-- connect4.py
`-- README.md
```

## Possible Improvements

- Add a restart button
- Detect when the board is full and declare a draw
- Add a computer-controlled opponent
- Include a score tracker
- Add sound effects and animations
- Let players choose their colors

## Troubleshooting

### Pygame or NumPy is not installed

Install both packages with:

```bash
python -m pip install pygame numpy
```

### The game window does not open

Make sure you are running the script in a desktop environment that supports graphical windows.

### A full column does not accept a piece

This is expected. Choose another column that still has an empty space.

## About

This project is a simple demonstration of game logic, event handling, array-based board management, and graphical programming with Python.

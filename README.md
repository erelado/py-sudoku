# py-sudoku (console)

## 📙 Description
A simple Python program that generates and solves Sudoku board (9x9) puzzles.

### 📏 Scope
The goal of the project was to examine Python's basic syntax and provide added educational value.

The first part of the project was to create a sudoku board solver.
A sudoku board generator was later added to the project.

### 🔗 References
Inspiration taken from:
- [jeffsieu / py-sudoku](https://github.com/jeffsieu/py-sudoku).
- [techwithtim](https://www.youtube.com/watch?v=eqUwSA0xI-s&list=PLzMcBGfZo4-kE3aF6Y0wNBNih7hWRAU2o) / [Sudoku-GUI-Solver](https://github.com/techwithtim/Sudoku-GUI-Solver).

\
&nbsp;

# 🚩 Usage

### Generating a Sudoku board
```py
from Sudoku import SudokuBoardGenerator, SudokuBoardSolver, print_board

puzzle = SudokuBoardGenerator()    # Initializion.
puzzle.generate_unsolved_board(5)  # Sudoku board generation (difficulty = 5 attempts).
print_board(puzzle.board)          # Printing the result.

# Generating a new Sudoku board to solve...
# generated a new board in 1.1324846744537354 seconds

# 0 0 0 | 6 0 5 | 8 1 7
# 0 0 6 | 0 0 0 | 2 0 0
# 4 5 0 | 7 0 0 | 6 3 0
# ------|-------|------
# 9 0 0 | 0 7 3 | 0 0 0
# 0 6 0 | 0 0 0 | 0 0 0
# 2 7 3 | 9 0 0 | 0 0 0
# ------|-------|------
# 0 0 1 | 0 8 0 | 0 0 0
# 0 0 0 | 0 3 0 | 1 4 8
# 0 0 0 | 0 0 9 | 0 7 0
```

### Solving a Sudoku board
Solving a board that has been pre-generated by the algorithm.
```py
from Sudoku import SudokuBoardGenerator, SudokuBoardSolver, print_board

# using the generated "puzzle"
puzzle = SudokuBoardGenerator()          # Generator initializion.
puzzle.generate_unsolved_board(5)        # Sudoku board generation.

solver = SudokuBoardSolver(puzzle.board) # Solver initializion.
solver.solve_board()                     # Sudoku board solution.
print_board(solver.board)                # Printing the result.

# Generating a new Sudoku board to solve...
# generated a new board in 1.1324846744537354 seconds

# solved in 0.03597092628479004 seconds

# 5 3 2 | 4 1 9 | 7 6 8
# 1 7 8 | 5 3 6 | 2 4 9
# 9 4 6 | 8 7 2 | 3 5 1
# ------|-------|------
# 8 1 4 | 2 5 3 | 9 7 6
# 2 9 7 | 6 4 1 | 8 3 5
# 6 5 3 | 7 9 8 | 1 2 4
# ------|-------|------
# 4 6 9 | 1 2 7 | 5 8 3
# 3 2 5 | 9 8 4 | 6 1 7
# 7 8 1 | 3 6 5 | 4 9 2
```

### Importing boards
You can also import Sudoku boards from an outsourcer.
```py
from Sudoku import SudokuBoardGenerator, SudokuBoardSolver, print_board

# using "World's hardest sudoku: can you crack it?"
# @ https://www.telegraph.co.uk/news/science/science-news/9359579/Worlds-hardest-sudoku-can-you-crack-it.html
hardest_sudoku = [
    [8,0,0,0,0,0,0,0,0],
    [0,0,3,6,0,0,0,0,0],
    [0,7,0,0,9,0,2,0,0],
    [0,5,0,0,0,7,0,0,0],
    [0,0,0,0,4,5,7,0,0],
    [0,0,0,1,0,0,0,3,0],
    [0,0,1,0,0,0,0,6,8],
    [0,0,8,5,0,0,0,1,0],
    [0,9,0,0,0,0,4,0,0]
    ]

solver = SudokuBoardSolver(hardest_sudoku) # Solver initializion.
solver.solve_board()                       # Sudoku board solution.
print_board(solver.board)                  # Printing the result.

# solved in 1.8471145629882812 seconds

# 8 1 2 | 7 5 3 | 6 4 9
# 9 4 3 | 6 8 2 | 1 7 5
# 6 7 5 | 4 9 1 | 2 8 3
# ------|-------|------
# 1 5 4 | 2 3 7 | 8 9 6
# 3 6 9 | 8 4 5 | 7 2 1
# 2 8 7 | 1 6 9 | 5 3 4
# ------|-------|------
# 5 2 1 | 9 7 4 | 3 6 8
# 4 3 8 | 5 2 6 | 9 1 7
# 7 9 6 | 3 1 8 | 4 5 2
```
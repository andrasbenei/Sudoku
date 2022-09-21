# Sudoku with solver and GUI

## Description

I created a Sudoku earlier withouth graphical interface, which worked fine but I missed the GUI. Later I saw a project on TechWithTim's Youtube channel in which he created a Sudoku a bit differently, with GUI (pygame). Inspired by that, I modified my script and added the interface.

The script provides the User a board with 20 given numbers. The User can place numbers in the board according to the rules of Sudoku. The User can also make the script solve the board with backtracking method. In this case the script shows the steps with some delay so the User can follow them.

Note: the goal of this project was to create the algorithm and make some GUI, not to make a full working game. Altough I see its incompleteness, I'm not planning to improve the script regarding its playing experience.

## How to use

The script imports the pre-made boards from boards.py and chooses one from them by random. These boards contain 20 given numbers. The User can select the empty cells and add a number. Once the User pushed Enter, the script:
- checks if the given number follows the rules of Sudoku
- solves the board in the background (if possible with the given number)
- if both of the above are True: changes the color of the new number from grey to black
- if at least one of the above is False: deletes the new number from the cell and removes one life from the User (showed by a red X in the left corner).

The User has 5 lifes.

By pushing the Space button, the User can make the script solve the board with the backtracking method:
- find the next empty cell
- place numbers in the cell from 1 to 9, until the first valid (Sudoku rules) number is found
- if none of the numbers are valid: go back to the previous cell, increase the number until the next valid number is found, then move on the next empty cell again

The solver script takes 10 milliseconds delay when changing cell (to the next empty or to the previous one), which makes the process visible for the User. Also, for those cells which were filled by the solver script, it uses green edges for the validated cells, and red edges for those where it must change the validated value.

## Improvement ideas

This backtracking method is popular, but it's probably not the most efficient way to solve this game, the solver script runs quite long sometimes. Although currently I'm not planning to spend more time with this project, but later I may come back to it and try to find a faster solution. My idea is to simulate how a human would solve a Sudoku, and compare that's efficiency with this method's.

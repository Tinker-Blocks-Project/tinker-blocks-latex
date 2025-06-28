# Tinker Blocks Project

An educational tool that teaches programming concepts through physical blocks and a programmable car. Children arrange programming blocks (like MOV, LOOP, IF) on a grid board to control a car that can do various tasks.

## Features

### 1. Programming Grid

This is the physical grid where you place the programming blocks

#### Programming Blocks

- Square shaped, each representing a programming statement (IF, Loop, Mov, Integers, etc...)
- The syntax uses Indentation for scoping similar to Python syntax. This is much easier for interpretation that curly brackets.

#### RasperryPi

- Performs all control signals and processing (Image Processing, Machine Learning, etc...)
- Its also connected to an LCD screen that displays information about the current game mode. With buttons (or Joystick) to control the LCD.
- The LCD always has a "Run" button which simply executes the code currently programmed on the grid and moves the car accordingly, whatever the game mode is.

#### Image Processing

- The grid has a camera to capture its state on each run and the image will be sent to the RasperryPi which will perform Image Processing to understand the grid.
- Each block will have a color or a symbol to be detectable.

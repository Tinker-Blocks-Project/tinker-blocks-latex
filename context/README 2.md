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

### 2. Game Modes

#### A. Race Mode

- In this mode, we have a big plane surface with a path outlined by black tapes and the goal is to program the car to reach the end-line with the fewest number of runs and least time without hitting a black tape (going out the path)
- When the mode starts it detects that the car should be on the yellow (start) tape so that the child can start executing runs to reach the end line.
- When the car hits the path we perform a reverse sequence of operations to move the car back to its original position before the run so that the child can run it again.
- The child is not allowed to move the car manually (sensors will perform cheat detection mechanisms)
- Once the car detects the red (end) tape the child wins and we display the score.

#### B. Shape Drawer

- We have a white board that the car should be placed on. In the game mode settings the child chooses a shape and starts.
- The goal is to program the car to draw the shape in the least number of runs and time.
- The car has a pen the can be lowered and raised (with corresponding blocks) so that the child can choose when to draw and when to just move the car.
- When the child chooses to submit their drawing, we run it through our ML model that will calculate the accuracy of the drawing and that is their score.
- To run their drawing on our model, the RasperryPi will also simulate the drawing while we execute the commands and move the car, to create a virtual image of their drawing.

#### C. Free Mode

- A fun mode where the child can perform whatever operations they want on the car and move it around by executing runs.

### 3. The Car

- Dual wheel encoders for precise movement tracking.
- Line sensors for path boundary detection.
- MPU6050 (accelerometer + gyroscope) for precise rotation.
- Servo-controlled pen mechanism for lowering and raising.

## Hardware Components

### Car Module

- Two of H-Bridge Motor Driver.
- Four DC Motors.
- A Whiteboard Pen With Servo Motor.
- Servo Motor for the front tiers.
- Two IR Sensors on the front tiers (to detect of tape for game mode 1).
- Gyroscope MPU6050.
- Microcontroller Arduino Mega.
- Ultrasonic Sensor for detection of obstacles.

### Wooden Board

- Raspberry Pi 4 (4Gb RAM).
- Keypad for all buttons controlling the game (start , run , next , previous).
- LCD for displaying the status of game and choices.
- A Camera above the board to read it.


## Diagrams

### Use Case Flow

![Use Case Flow](../assets/UseCaseFlow.jpg)

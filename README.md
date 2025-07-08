# MouseMaze

## PROJECT PROMPT
You are going to have your code do an algorithm to simulate a mouse going
through an 8 x 8 maze (shown to the right). The top left square in the maze
is position 0,0. The squares that are colored black indicate that there is a
wall in that position.
The mouse will continuously move through the maze. Each loop iteration it
makes one step (i.e., moves one block). The direction of the step is determined
by the function found in the Arduino library: random(3); which will return a
value between 0 and 3. 0 is North (up), 1 is East, 2 is South and 3 is West. The mouse
should move in the given direction unless there is a wall. In that case it should
stay in the same position. Each loop iteration, you should indicate through the serial
port the direction tried and the location of the mouse after the step. You also should keep track of how many
steps the mouse made (a failed step should still be counted as a step).
The default start location for the mouse is (4,0) and the default end location is (4,7). The mouse should
continuously “go” from the given start location to the given end location. The program should indicate the
number of steps the mouse took when reaching the end location by printing the number to the serial port.
The count should reset when the mouse starts again.
If a new start location (2 integers) and end location (2 integers) are sent across the serial port as a series of 4
integers all on one line (assume the person using the serial port does so correctly and within range), they
should become the new start and end locations for the next time the mouse goes through the maze and there
after.

This project is a code for an Arduino Uno that uses serial communication to:

* Communicate the position of a "mouse" in a "maze"
* Anticipate the next move of the mouse
* Validate and execute the move if possible
* Describe the moves required to finish the maze and the ratio of valid to invalid moves taken by the mouse.

Funcitons Used:

* wall()
  - Boolean function that returns false if the planned position collides with a wall
* destination()
  - Integer returning function that uses a random number generator (0-3) to determine which direction the mouse travels for the planned move, and then returns the number for indexing purposes.
* boundaryCheck()
  - Boolean function that returns false if the mouse's planned move is outside of the boundaries of the grid
* moveSuccess()
  - changes the current position to the planned position
* moveFail()
  - changes the planned position to the current position (undoes any changes)
* dialogue()
  - communicates the current position and planned of the mouse through the serial monitor

The mouse starts in the northwest corner of the grid. With each iteraton the mouse will plan a move.  If the move doesn't coincide with a wall or boundary the mouse will go to the new position in the grid.  This continues until the mouse reaches the end, where the serial monitor displays the moves taken and efficiency of the mouse.

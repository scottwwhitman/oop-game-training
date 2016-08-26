<!--
Creator: <Name>
Location: SF
-->

#Scott Whitman: Racing Game Model

#### Original code repository link: https://github.com/sf-wdi-31/oop-game-training

### User Stories & Game Mechanics
1. The two players can see the race course.
2. Each player is asked to enter their name.
3. Each player is asked to select their car from several choices.
4. After each player selects their car, the board is set with the two cars at the start line.
5. The players hit a 'go' button and a '3, 2, 1, Go!' countdown commences.
6. After "Go!" each player taps a selected key to make their car move.
7. With each key tap a number randomizer assigns each car with the distance it will move.
8. A player wins when their car crosses the finish line first at a pre-determined distance.


### Data Structures for "Memory" (Independent Practice)

**CarTypes**
  - `carType` (Car image)

**PlayerCar**
  - `playerName` (string)
  - `carType` (Car image)
  - `distanceTraveled` (number)
  - `moveCar()` (Function - moves car by the randomized distance given with each key stroke)
  - `createCar(options)` (Function - constructor, creates a car based on player name and carType chosen)

**ScoreBoard**
  - `Car1` (number)
  - `Car2` (number)

**Game**
  - `setCars()` (Function - places the two cars in the start position)
  - `startCountdown()` (Function - timer to start the race and activate the player race keys)
  - `randomizeDistance()` (Function - random number generator creates randomized distance car can travel with each key stroke)
  - `playAgain()` (Function - places the two cars back at the start line and sets a new race)
  - `reset()` (Function - clears the cars and the scores and resets the game!)
  - `hasWon()` (Function - check if either of the cars has won!)
  - `celebrate()` (Function - display a win message with the winners name)
  - `addWinner()` (Function - adds 1 point to the score of the car who won)


### Development Stories

1. Players can see the race course.
  * Create HTML structure to display the racecourse.
  * Need a button to run `createCar` constructor for each player to add `playerName` and select `carType` and adds each car to the page with the `setCars` function.
  * Activate a click event listener to the start button once both cars have been placed on the race course.

2. Players hit the start button to initiate the `startCountdown()` function.
  * Once timer countdown is complete adds keystrokes event listeners to each players designated key that allows players to begin the race

3. Players begin to tap their designated keys.
  * Each time a keystroke occurs the `randomizeDistance()` function generates a distance for the corresponding car and adds the distance to `distanceTraveled` and the `moveCar()` function moves the corresponding car the equivalent distance added
  * After each keystroke the `hasWon()` function checks each cars `distanceTraveled` to see if either car has gone the required distance to win
  * This process repeats until a car has won

4. A car wins when it has gone the required distance to the finish line:
  * The keystroke event listener for both players keys are turned off and the cars stop
  * The `celebrate()` function displays the name of the car who won
  * The `addWinner()` function adds one point to the winning car on the ScoreBoard
  * A click event listener is turned on for the "Play Again" button, which runs the `playAgain()` function and retains the scores on the ScoreBoard, and then turned off again once the `playAgain()` function is run
  * The `reset()` function resets the entire game, allowing new players to choose their names and cars


###Potential Challenges / Development Questions

1. Giving players custom images
2. Starting a new race while retaining each players cars and the score board
3. Building in the random number generator to calculate the distance traveled


### Deliverable

Design user stories, data structures, development stories, and potential challenges for a **racing game** in which two players use the keyboard to control "cars" that race across the screen.

Here are some popular bonus features that would affect your data structure plan:

1. How would you make your player's "cars" use custom images?
2. Can a player type in their name to see custom win messages?
3. Can you enable a reset button to restart the race?
4. How about a win counter that spans across multiple races?

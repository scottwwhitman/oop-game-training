<!--
Creator: <Name>
Location: SF
-->

![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

#Training: Model a Game with OOP

### Example: Memory

#### User Stories & Game Mechanics
1. A user can see a set of face-down cards.
2. A user can select a card to "flip it over" and see its other side.
3. If the user flips two matching cards face-up at the same time, the cards will be removed from the game.
4. If the user flips two non-matching cards face-up at the same time, both cards will turn back face down.
5. The user wins when they've matched all the cards!

#### Check for Understanding

What are some data structures we might use when building a Memory game?

<details><summary>click to see examples</summary>
  Did you think of making a `Card` object type? A `Game`?
</details>

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

#### Independent Practice: Data Structures for "Memory"
Let's consider object types Card, Game, and Pair.

Work with a partner to list some properties and methods of cards, the game itself, and a particular pair.

* List the type of each property (number, boolean, `Card`, etc.).
* List the parameters that each method will take.
* Don't forget a constructor!

**Card**
<details><summary>click for examples properties</summary>
  - `faceImage` (string)
  - `isFaceUp` (boolean)
  - `isMatched` (boolean)
  - `flipOver()` (Function - change whether the card is currently face up)
  - `Card(options)` (Function - constructor, create a card based on options like whether it should be a random image or what the image should be)
</details>

**Pair**
<details><summary>click for examples for Pair</summary>
  - `card1` (Card)
  - `card2` (Card)
  - `addCard(someCard)` (Function - add a specific card to the pair)
  - `isMatch()` (Function - check if this pair is a match)
  - `Pair()` (Function - constructor, create an empty pair)
</details>

**Game**
<details><summary>click for examples for Game</summary>
  - `current_guess` (Pair)
  - `cards` ([Card])
  - `reset()` (Function - resets the game!)
  - `randomize()` (Function - creates randomized game)
  - `Game(numCards)` (Function - constructor)
  - `removeCard(card)` (Function - remove this card from the game)
</details>

#### Development Stories
1. A user can see a set of face-down cards.
  * Create HTML structure to display cards on screen (Handlebars?).
  * Ensure that cards start out displayed face-down (in `Card` constructor?).

2. A user can select a card to "flip it over" and see its other side.
  * Add click event listener to cards that:
     - shows the other side of the card (`flipOver`)
     - creates or updates a pair (don't add same card twice though!)
     - checks if the cards in the pair match (`isMatch`)
     - continues according to result (see 3 and 4, below)

3. If the user flips two matching cards face-up at the same time, the cards will be removed from the game.
  * Assuming `isMatch()` gave true for the current pair:
    - set a short timer so the user can see that the cards matched (`setTimeout`), then...
    - replace each card in the pair with a "blank space" image to let user know it's been removed
    - use `off` to take off the click event listener from both cards
    - remove both cards from the game's list of cards

4. If the user flips two non-matching cards face-up at the same time, both cards will turn back face down.
  * Assuming `isMatch()` gave false for the current pair:
    - set a short timer so the user can see the cards (`setTimeout`), then...
    - flip each card in the pair back over so they're face-down

5. The user wins when they've matched all the cards!
  * Every time there is a match, the Game should also check if its cards array is now empty. If so, show a win screen.



### Deliverable

Design user stories, data structures, development stories, and potential challenges for a **racing game** in which two players use the keyboard to control "cars" that race across the screen.

As you work, you can edit this README to add a section at the top with your name, a link to the original repository, and a 3-5 sentence reflection on completing this assignment. Push your updates to GitHub and add a link to the repo to the "My Work" section of your website!
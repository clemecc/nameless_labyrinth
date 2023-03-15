# Labyrinth Description and Software Implementation details

## Labyrinth Game Description

Labyrinth (formerly The aMAZEing Labyrinth) has spawned a whole line of Labyrinth games. The game board has a set of tiles fixed solidly onto it; the remaining tiles that make up the labyrinth slide in and out of the rows created by the tiles that are locked in place. One tile always remains outside the labyrinth, and players take turns taking this extra tile and sliding it into a row of the labyrinth, moving all those tiles and pushing one out the other side of the board ; this newly removed tile becomes the piece for the next player to add to the maze.

Players move around the shifting paths of the labyrinth in a race to collect various treasures. Whoever collects all of his treasures first and returns to his home space wins!

## Things to model and how

- 4 pawns/players: class objects attributed to each player in the game. Attributes:
  - player name as string
  - color as a string or int
  - list of treasure objectives
- 50 tiles: class objects, all their information is kept in initializing files that represent them. Attributes:
  - booleans for the open/closed nature of the sides
  - string for the treasure placed on the tile
  - filepath for background image
  - player/pawn object present on tile
  - boolean for the movable state of the tile
- The board: class objects containing the game board and other game state variables. Attributes:
  - grid to be implemented by a dict with keys as position tuples and values as the tiles
  - hand containing the tile to be played on each turn
  - previous position of the hand on the grid

## Unrolling of the game

### Initialisation

Choose the number of players (optional : name the players) and launch the game. Initialize the board with its fixed tiles, then place randomly (orientand order) all the other tiles. Place the pawns on the board. Distribute the treasures to the players.

### A player’s turn

The player chooses the orientation of his tile and in which line or column. The tiles are slid along their line/column. The rules are: The path tile cannot be inserted back into the board at the same place where it was pushed out. If the path tile you push out has a playing piece on it, put this piece on the opposite side of the board on the path tile that was just placed. Moving this piece does not count as your turn!

Then the player can choose the tile to which they want to go (the software will check that it is possible). The goal for them is to reach his next “objective”/ treasure until they have none left.

### End of game

The game is over and won by the first player to find all their treasures.

## The GUI

- Game parameters and starting window
- Current game canvas divided in grid display, and other game state variables like current hand, treasure objectives etc
- End of game screen and high scores table

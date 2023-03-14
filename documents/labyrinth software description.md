# Labyrinth Description and Software Implementation details

## Labyrinth Game Description

Labyrinth (formerly The aMAZEing Labyrinth) has spawned a whole line of Labyrinth games. The game board has a set of tiles fixed solidly onto it; the remaining tiles that make up the labyrinth slide in and out of the rows created by the tiles that are locked in place. One tile always remains outside the labyrinth, and players take turns taking this extra tile and sliding it into a row of the labyrinth, moving all those tiles and pushing one out the other side of the board ; this newly removed tile becomes the piece for the next player to add to the maze.

Players move around the shifting paths of the labyrinth in a race to collect various treasures. Whoever collects all of his treasures first and returns to his home space wins !

## Things to model and how

- 4 pawns: specific object described by its identifier, its color, its position on the board, the list of its objectives
- 50 tiles: specific object, all its information is kept in an initializing file. Description: treasure, boolean saying if it is fixed or not / the position on the board ?, 4 booleans giving the existence or not of a path
- The treasures: a list of the name of the treasures
- The board: a 2D list or a dictionary keeping the order of all the tiles and their orientation

## Unrolling of the game

### Initialisation

Choose the number of players (optional : name the players) and launch the game. Place the fixed tiles on the board, then place randomly (orientation and order) all the other tiles. Place the pawns on the board. Distribute the treasures to the players.

### A player’s turn

The player chooses the orientation of his tile and in which line or column. The tiles are rotated along their line/column. The rules are : The path tile cannot be inserted back into the board at the same place where it was pushed out. If the path tile you push out has a playing piece on it, put this piece on the opposite side of the board on the path tile that was just placed. Moving this piece does not count as your turn !

Then the player can choose the tile to which he wants to go (the software will check that it is possible). The goal for him is to reach his “objective”/ treasure.

### End of game

The game is over when a player has found all of his treasures.

## The GUI

An initializing window asking for the number of players (and their username) with a start button and a quit button.

A canvas to display the tiles on the board. Texts or message boxes appearing and disappearing telling whose turn it is / notify errors. The pawns are represented as well. Arrows will show which line and column can be pushed and in which direction. In an area the current tile and the treasure to reach will be displayed. A button to rotate the current tile by a quarter turn will appear too.

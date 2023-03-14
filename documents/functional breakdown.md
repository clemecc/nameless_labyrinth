# Functional breakdown

## Data structures

- Classes representing:
  - Labyrinth tiles
  - Treasures
  - Pawns
  - Players

- Probable use of 2-dimensional lists for game board

## Program logic

- Players choose starting parameters
- Intitialisation of game state and objects
- Run game mainloop
  - orient tile
  - place tile (and verify that move is allowed)
  - move pawn (and check validity)
  - check objectives conpletion and win conditions
  - give control to next player or end game
- Congratulate winner

## GUI

- Start menu & game init
- Game board display
- Game state display
- Game control interface

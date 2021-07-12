# Pacman Kata

This kata is based off the well known game pacman. Pacman finds himself in a grid filled with monsters. Will he be able to eat all the dots on the board before the monsters eat him?

## Task

Incomplete list of things the game needs:

- pacman is on a grid filled with dots
- pacman has a direction
- pacman moves on each tick
- user can rotate pacman
- pacman eats dots
- pacman wraps around
- pacman stops on wall
- pacman will not rotate into a wall
- game score (levels completed, number of dots eaten in this level)
- monsters…
- levels
- animate pacman eating (mouth opens and closes)

## Representing Pacman

Representation does not have to be difficult. E.g. pacman starts in the centre of the board and is looking up (notice that pacman eats, so the V points downward because pacman has his mouth open):

~~~
. . .
.V.
. . .
~~~

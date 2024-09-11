---
description: "Zhifeng's Reflections on the Connect Four solver and his development process."
long_title: "Solving Con4 Reflections - Zhifeng"
---

# Reflections

There are a lot of thoughts coming up about the general concepts of solving a game, implementation details specifically for Connect Four, and others like the project structure.

The general concepts of game solving discuss my thoughts about what games are easily computer-solvable. I'm pretty curious about the minimum information that needs to be stored to make instant decisions on any valid states. For example, Victor Allis mentioned several knowledge-based ways of solving the game involving counting zugzwangs, .etc. I wonder how machines can conclude knowledge like this.

The implementation discussion will discuss the merit of using bits to represent Connect Four game states.

# Thoughts on games and game-solving algorithms

Connect Four is a perfect game for algorithms, and it's also a perfect start for me to learn and feel how traditional game solving alogrithms work (without a machine learning based search pruning I guess).

## Connect Four Characteristics

### Easy for computers to represent

The first point would be "easy computer representation." All the information of every game state should be easy and efficient for computers to represent, like not involving floats or complex math calculations or memory operations. I guess all of the popular human games would fit into that to be popular among humans. Perhaps one exception would be Math itself? Maybe, in some sense, Math is a game about transforming equations with legal math operations. Representing Math equations might need trees for syntax. I think it would definitely be harder for computers to represent, compared with a 7 \* 6 array (or inside a 64-bit number) representing Connect Four.

### Clear terminal states

The second point is "clear terminal states." For a computer to smoothly solve, a game would better have easy and efficient ways to determine its termination. For example, terminal states for Connect Four are relatively simple to calculate, especially when representing them in bits. However, like the Game of Go, for human players, the game often terminates in the middle when a player feels there is no chance. Even if the game goes into the end, there will always be many legal moves that are still playable. I guess, strictly speaking, the true terminal state would be the board only containing legal moves about loops of a single stone.

### No loops

The third point would be whether a game has "loops." Connect Four doesn't contain loops. The 1111 game contains loops, and it is common that the player leaving the loop first would be the one to lose. I guess that might be one of the reasons preventing some games from being popular. There has to be a clear winner for people to chat about.

# Implementation Reflections

## Bits representation of Connect Four

The most significant merit of Pascal Cons’ design would be the bit-representation of states of the Connect Four Game, more specifically, the extra layer of bits “at the top of“ the game board preventing overflows when trying to get the bit position of the next move. I guess this design also prevents counting vertical winning positions into another column.

The bit representation automatically provides tons of convenience in calculating winning positions and passing states between layers of recursion. For example, all you need to do to find a possible vertical winning position is to “bit-and” three up-shifted masks representing the player’s stones.

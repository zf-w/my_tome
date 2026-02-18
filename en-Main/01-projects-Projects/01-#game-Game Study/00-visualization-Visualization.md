---
description: "Discussing about visualizing the Connect Four game."
long_title: "Connect Four Visualization - Zhifeng"
---

# Visualizing Connect Four

The gadget below is an interactive visualization of all Connect Four game states within five steps from the empty-board game state. The visualization consists of two parts: the 3D network (graph) visualization and the game board. We can use the game board to navigate through the states while seeing the change of paths in the network visualization above the board.

```json#con4_graph
{
    "load": ["/src/assets/c4w7h6.len5.20240803.gamegraph.json"],
    "following_actions_string": "4757",
    "api_url": "https://con4.zf-w.space/c4w7h6",
    "camera_param": {
        "z": 1.5
    },
    "orbit_ctrl_param": {
        "auto_rotate_speed": 0.1
    }
}
```

> - Info:
>   - The Connect Four Visualization has two parts: the graph viz and the board.
>   - The graph(network) above consists of all the states within five moves starting from the empty board.
>   - Each dot represents a game state node, or say a board situation.
>   - Each line represents a valid move, or game action, edge.
>   - The color on dots and lines represents the all-player-play-optimally result: redder indicates the first-hand player wins quicker; more blue indicates the second-hand player wins quicker.
> - Control:
>   - Holding "left mouse button" + moving: rotate the graph.
>   - Holding "right mouse button" + moving: move the graph around.
>   - Holding "shift" + scrolling: zoom in or out.
>   - Click the play button under the game board: play the respective move on that column.

# Components of the Visualization

The visualization consists of three parts:

- The game graph visualization: a graph visualization of game states (partial) which the color of the dots represents the both-player-play-optimally result.
- The board: the Connect Four game board.

## Game Graph Visualization

With game states as nodes and actions as edges, we can get a game graph. With graph visualization algorithms, we can calculate each node's position that generally makes its in-graph neighbours positionally close.

For Connect Four, since two horizontally symmetric states have no fundamental difference, I have merged those states into one to visualize more states. I guess it would also be possible to not merge those states and visualize the game or even not consider the "same state formed by different paths" and just visualize the game graph as a seven-ary tree.

### Game State Dot

Each game state has a score representing the optimal(both players playing their optimal moves) terminal game result for the player playing that state. To make the coloring more informational, the scores were altered to reflect the game result of the player playing the root state. Currently, the more red the dot in the graph visualization is, the quicker the first player will win. The more blue the dot is, the quicker the second player will win.

### Edges in Graph

The edges in the graph represent actions between game states. For Connect Four, there are no bidirectional edges. The ends of the edges are in black to accommodate the "rust-navy" theme, so the edges are like sharp pointers in the dark theme. The coloring for the light theme will be added in the future.

Currently, the color of the "from" end is the color of the "to" state, so we can easily tell whether an edge is leading to quicker winning or losing.

### Rotating the Graph

While the cursor is on the graph, we can rotate it by holding the left button and moving the mouse or touch-and-move for touch screens. The graph automatically focuses on the average point of the nodes on the current path from the "base" game state of the visualization. In addition, although the zooming feature is disabled for not interrupting the default scrolling of the book, the zooming feature is enabled in the "demo" version of the visualization.

## Board

The board represents the Connect Four game board. We can tell different players' stones(discs, pieces, etc.) by whether a stone is filled or hollow for its style. This design tries to accommodate different color themes. In addition to whether an entry contains a stone and which player a stone belongs to, the number inside the stone informs us of the sequence of moves played by the two players. For the current design, the sequence starts with zero, meaning the stones with even numbers belong to the first-hand player while the stones with odd numbers belong to the other player.

### Control Panel

The control panel allows us to play the game and add stones to the board by clicking the "play" buttons below. I guess these "buttons" are not very intuitive for users to see as clickable buttons, but wrapping those texts with borders is also a little bit strange to me. The "play" buttons should be aligned with the columns of the board for us to play.

Below the "play" buttons, there are also a "undo" button. The "undo" button removes the most recent stone or "move. The base state is built-in for each game visualization, allowing a closer examination of "endgames" or "subgames" starting from a specific state instead of the "root" empty game board.

## Information about Game States

### Score of a Game State

For the score of a state, the current design follows Pascal Pons' [blog](http://blog.gamesolver.org)'s scoring design. If the score is positive, it represents the number, or index, of the quickest possible stones, counting from the last stone, which the current player can use it to win the game. If the score is negative, on the other hand, it represents how quickly the current player's opponent can win the game. If the score is zero, the game will end with a draw if both players play their optimal moves possible. For example, if not changed, the above game state has a score of -18 because the current player is going to lose with their opponent's 4th stone, the 18th stone counting back from the 21st stone. Since the current game board has a width of 7 and a height of 6, each player has 21 stones.

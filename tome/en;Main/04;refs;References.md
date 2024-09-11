---
description: "I listed some of the major readings I have been focusing on for better transparency and to be more helpful."
long_title: "My References - Zhifeng"
---

# References:

This page lists some of my major references of my projects. I have read those papers in detail, to a reproducing-replicating level.

## Pascal Pons' Blogs about Solving Connect Four

- Link: [blog.gamesolver.org (Last Accessed: 2024-05-25)](http://blog.gamesolver.org)

- GitHub Repository : [github.com/PascalPons/connect4 (Last Accessed: 2024-05-25)](https://github.com/PascalPons/connect4)

Pascal Pons' blogs discusses how to use various of algorithms and optimization techniques to solve the game Connect Four. Pascal iteratively introduced the concepts from shallow to deep: from how to represent a Connect Four state in computer to how to use memorizations to accelerate the computing process.

I have reproduced, using the original code from the author, and replicated, writing my own code with the same idea, the results. I'm trying to learn a general sense of how the alpha-beta algorithm works.  Sometimes, I feel that why the algorithm can return the lower bound without getting a valid result is slightly confusing. I'm trying to make visualizations about this to see the algorithm's behavior in detail.

## Yifan Hu's Paper: Efficient, High-Quality Force-Directed Graph Drawing

- Link: [yifanhu.net/PUB/graph_draw.pdf (Last Accessed: 2024-05-05)](http://yifanhu.net/PUB/graph_draw.pdf)

The author introduced the concepts of graph visualization, goals of graph visualization, naive force-directed graph layout, graph corsening and multi-level layout, and Barnes-Hut tree for N-body calculation acceleration.

I have replicated the result of the Multi-level Force-directed Graph Layout algorithm, including one of the graph coarsening algorithm, force-directed graph layout algorithm, and the Barnes-Hut tree N-body force calculation data structure. I have implemented these in Python around 2020, C++ arround 2023, and Rust (in progress).

# Read

## Victor Allis's paper about A Knowledge Based Approach of Connect Four

- APA: Allis, Louis Victor. "A Knowledge-Based Approach of Connect-Four." J. _Int. Comput. Games Assoc._ 11.4 (1988): 165

- Link : [rainer-rosenberger.de/x_spiele/download/connect4_victor_allis.pdf (Last Accessed: 2024-04-21)](https://rainer-rosenberger.de/x_spiele/download/connect4_victor_allis.pdf)

This is the paper I got confused about after it got into the knowledge-based part. But I feel it's getting clearer after I had my "demo"'s help. But with more experience in implementing the first-sight state game bound calculation. For example, if our opponent got two immediate winning positions in two different columns or one atop the one immediate one, we lose.

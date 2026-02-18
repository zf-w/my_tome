---
description: "My individual independent project on game study: solving Connect Four game."
long_title: "Solving Connect Four - Zhifeng"
---

# Game Study: Solving Connect Four

```json#con4_graph
{
    "load": ["/src/assets/c4w7h6.len5.20240803.gamegraph.json"],
    "following_actions_string": "2737",
    "api_url": "https://www.zf-w.space/api/c4w7h6/solve",
    "camera_param": {
        "z": 2.0
    },
    "orbit_ctrl_param": {
        "auto_rotate_speed": 0.1
    }
}
```

# Learning to Solve Connect Four

I have been thinking about learning to solve classic board games like Connect 4 and Game of Go for a long time. Finally, during the winter holiday of 2024, I have some time to study the Connect Four Solving. By studying the blog [http://blog.gamesolver.org](http://blog.gamesolver.org), I have implemented the game solver, calculated the opening book, and combined it with a server backend and frontend webpage.

# What did I do

- Reproduced and Replicated the results of Pascal Pons' blog "Solving Connect 4: How to build a perfect AI": [http://blog.gamesolver.org](http://blog.gamesolver.org).

- Calculated Connect Four opening books for quicker calculation.

- Designed the frontend demo and deployed the Connect Four solver to the backend server.

- Visualize the partial game graph with my previous Barnes-Hut tree implementation and graph layout algorithm.

- Designed the above visualization.

# Timeline

- Aug 2024: Designing interative visualizations embedded in my Markdown Tome format.

- May 2024: Starting to make Connect Four game graph visualizations.

- Febuary 2024: Starting to think about how to improve the generation process of opening books.

- January 2024: I managed to write my own Connect Four Solver in Rust-Lang, first in command line, later on web with graphic interface. I had a simple opening book storing the first several levels of state results, but that is not fast enough.

- December 2023: I finally had some time and powerful tools like the variable naming, memory safety and ownership, testing, and project file structure paradigms of Rust-Lang to learn and build my Connect Four solver.

- December 2021: I took a Kaggle course about game solving and wondered if there are established theories for solving Connect Four without Machine Learning. Then, I found Victor Allis's paper: A Knowledge-Based Approach of Connect Four. I guess he must be thinking a lot about the game and computational strategies. Some of his ideas are not intuitive to me. Thus, I think I might need to first use a somewhat brute-force approach to solve Connect Four and then build some interactive tools to help me understand his knowledge-based approach.

# Challenges

I think, currently, the most significant challenge is to think about how to formalize and divide the whole game implementation - game solving - game visualization processes. The whole project is, in my opinion, a lot of work, and how can we divide it into multiple managable, testable, and reusable components is the biggest problem to think about to me. For example, when writing the Negamax algorithm for Connect Four, we might need to think about what are the key functionalities or characteristics that make the game solvable and how to express those behaviors.

# General Tech stack

- Core: Rust Programming Language:

This programming language and its core conceptual design really help me to think and design more carefully and, as a result, quicker and safer. The Rust Programming Language also has a well-designed project structure and tutorial readings.

- Backend: Rust-Actix-Web

A Rust web library that enables me to fairly easily connect my Connect Four solving codes onto it with its design that allows passing shared information between threads.

- Backend: Heroku

Heroku is a platform as a service that enables developers to build, run, and operate applications in the cloud. I find its workflow very convenient. I learned how to make my own build pack and deployed the whole thing with the push of a button.

- Frontend: Vanilla JavaScript + Three.js Web 3D Library

I have designed my own static pages rendering system.

- Version Control: Git+GitHub

---
description: "Readings I have read to make the demo."
long_title: "Solving Con4 References - Zhifeng"
---

# Main Concepts References

## Pascal Pons' article and GitHub Repository

Link: [To My Reference](/reading/)

Pascal Pons' blogs discusses how to use various of algorithms and optimization techniques to solve the game Connect Four. Pascal iteratively introduced the concepts from shallow to deep: from how to represent a Connect Four state in computer to how to use memorizations to accelerate the computing process.

I have reproduced and replicated the results. I'm trying to learn a general sense of how the alpha-beta algorithm works. Sometimes, I feel that why the algorithm can return the lower bound without getting a valid result is slightly confusing. I'm trying to make visualizations about this to see the algorithm's behavior in detail.

## Victor Allis's paper

Link: [To My Reference](/reading/)

This is the paper I got confused about after it got into the knowledge-based part. But I feel it's getting clearer after I had my "demo"'s help. But with more experience in implementing the first-sight state game bound calculation. For example, if our opponent got two immediate winning positions in two different columns or one atop the one immediate one, we lose.

# Other Helpful Resources

## Negamax with transposition table and alpha-beta pruning

The [Wikipedia page](https://en.wikipedia.org/wiki/Negamax) provides a clearer insight into the roles of upper and lower bounds in the pruning part. It validates my concern about the fact that pruned results are not accurate and require careful handling when storing them with memorization. I'm still a little bit confused about the whole picture of Negamax. I might need to make some visualizations.

# Developer References

## The Rust Programming Language (With Quiz)

Link: https://rust-book.cs.brown.edu/

I have read the book to learn the Rust Programming Language.

## The Cargo Book

Link: https://doc.rust-lang.org/cargo/

I have read the Section 2.5 Package Layout to learn project structure best practices and read Section 3.1. Specifying Dependencies for making my own project more atomic and reusable.

## Rust By Example

Link: https://doc.rust-lang.org/rust-by-example/generics/assoc_items/types.html

I have read Section 14.8.2 to learn the associated types for tidier programming interface and traits implementation, like "Game defines State" instead of "here is a game that implemented Game\<State\>."

## emk/heroku-buildpack-rust

Link: https://github.com/emk/heroku-buildpack-rust

I learned how to make a custom build pack that works with the Heroku cache directory.

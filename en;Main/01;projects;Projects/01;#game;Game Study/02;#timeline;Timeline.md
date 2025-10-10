---
description: "The timeline of Zhifeng's Game Study: Connect Four Solving Project."
long_title: "Timeline of Con4 Solving - Zhifeng"
---

# The Timeline of My Con4 Cog Game Project

## November 2022

In November 2022, I was working on my independent study of using maze games to understand human cognitive behaviors. Mazes are classic approaches to cognitive studies; for example, researchers let mice run through mazes and offer food to them as a reward to see how they learn to solve the maze and learn from rewards and mistakes.

While the maze can still be complicated for me to solve when the maze tree grows large and gives no immediate feedback, I wondered if there is something more fun for humans, complicated enough but still can be strongly solved such that we can still thoroughly evaluate each game move.

After a brief search through the popular games, I found the game of Connect Four to be fairly ideal: it's complicated but simple enough for computers.

## December 2023

With more tools and experience in software development, I was fairly ready to learn and implement my own Connect Four solver based on Pascal Pons's blog.

## February 2024

During the winter break of 2024, I managed to make the Connect Four solver run and deploy it to my web server.

### Challenge on Performance

The speed of the solver was not fast enough for the opening game states. Even though I have already implemented my version of the memorization tables learned from Pascal Pons' blog on solving Connect Four. It's difficult to find all the game states that are hard to solve at some level.

I tried to use a counter to count the number of states the algorithm searches for each game state, and this approach didn't work as I anticipated. Several months later, I realized the problem: a player might play a bad move and make a can-be-a-simple state much more complicated. I thought that's why a BFS from the empty game board that stops when meeting simple situations didn't work.

The work on that temporarily stopped, and I turned to focus on the game visualization and sustainable-documentation aspect of the problem.

## June 2024

One challenge of making visualizations would be how to nicely tag manuals and introductions along with the visualization. Previously, I tried to add a special help page about the controlling buttons and roles and purposes of each element in the graph. Emm, the result is not good enough from my point of view. Furthermore, I would also like to add reflections and design documentation along with the visualization. So, I figure I should probably embed visualizations into texts, which might solve the problems of designing `JavaScript` based buttons and `HTML` elements that covers the whole viewport as helping page.

In June 2024, I refactored the previous `Next.js` based tome rendering system into vanilla `JavaScript` to gain more understanding and more fundamental control. This was a good opportunity for me to redesign and embed my game visualization into the new structure.

## August 2024

The focus of August 2024 was on how to sustainably document my work and efforts. I think making my work more transparent for future research's reproducibility and replicability is essential. I kept polishing my documentation website.

## Future

The next step for me would be to implement some Connect Four machine learning AIs, for example, using a Large Language Model structure, and inspect and research their learning behaviors. I will design a Connect Four host platform or mechanism that can arrange games and record and analyze players', either human or AI, learning behavior.

For example, people take education to gain knowledge. Then, compared to self-play, would AIs learn faster with a leading "teacher" that guides its gameplay or sets up specific easy-to-learn "key point" game scenarios.

---
description: "The timeline of Zhifeng's Game Study: Connect Four Solving Project."
long_title: "Timeline of Con4 Solving - Zhifeng"
---

# The Timeline of My Con4 Solving Project

## June 2024

One challenge of making visualizations would be how to nicely tag manuals and introductions along with the visualization. Previously, I tried to add a special help page about the controlling buttons and roles and purposes of each element in the graph. Emm, the result is not good enough from my point of view. Furthermore, I would also like to add reflections and design documentation along with the visualization. So, I figure I should probably embed visualizations into texts, which might solve the problems of designing `JavaScript` based buttons and `HTML` elements that covers the whole viewport as helping page.

In June 2024, I refactored the previous `Next.js` based tome rendering system into vanilla `JavaScript` to gain more understanding and more fundamental control. This was a good opportunity for me to redesign and embed my game visualization into the new structure.

## February 2024

During the winter break of 2024, I managed to make the Connect Four solver run and deploy it to my web server, but the speed was not fast enough for the opening game states. Even though I have already implemented my version of the memorization tables learned from Pascal Pons' blog on solving Connect Four. It's difficult to find all the game states that are hard to solve at some level.

I tried to use a counter to count the number of states the algorithm searches for each game state, and this approach didn't work as I anticipated. Several months later, I realized the problem: a player might play a bad move and make a can-be-a-simple state much more complicated. I thought that's why a BFS from the empty game board that stops when meeting simple situations didn't work.

The work on that temporarily stopped, and I turned to focus on the game visualization aspect of the problem.
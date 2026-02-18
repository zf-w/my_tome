---
description: "My Graph Viz Reflections"
long_title: "My Graph Viz Project Reflections - Zhifeng"
---

# Graph Visualization

Graphs, or networks, are interesting ways to represent relationships between things. They are involved in many theories and applications. For example, a bunch of friends can be seen as a network of relations, in which each person can be seen as a vertex or node, and each relation can be seen as an edge. Say, if there is a thumbtack board, each thumbtack can represent a person, and lines between thumbtacks can represent relationships between people.

Then, here is the question: How can we place these thumbtacks such that the distances between thumbtacks generally reflect people's distances on the friend network? For example, thumbnails representing my direct friend should be closer to my thumbnail than those representing my friends' friends. Although I haven't been to any party, I guess it's a good question for introverted people to find their safe space among close friends instead of strangers.

That's the problem of Graph Visualization (in my understanding).

# The Algorithm

The algorithm is pretty intuitive. Still using our party example, if everyone tries to push away the strangers and pull their close friends closer, the party will gradually be more comfortable to me... or say physical distances between people more accuately reflect their friends social distance. In addition, there is an approach to make a graph simpler, visualize the simple graph first and then use the result to visualize the target graph. In a way, it's like (not exactly, but the idea) first making the relationship between some key people clear and then subsitituting the rest of the people into the simplified party. One of my independently figured-out ideas is that I can view those "introverted" people with fewer connections as the "key" people because they are, to some extent, more reasonable to stay at the outer part of the party. So, finding out their position makes it easier to put those "extroverted" popular people into the center. In a way, those introverted nodes are the frame of the party. I like that idea, though it is not true in the real world.

So, the algorithm generally consists of three parts:

## Graph Coarsening

This part of the algorithm simplifies, or coarsen or extract, the key structure out of the complex graph.

## Force Directed Graph Layout

The force-directed layout part simulates repulsive forces and attractive forces to pull structural neighbour nodes closer and push away unrelated nodes. In this way, the "cartesian" distance between nodes reflects the structural distance between nodes. I guess.

## Graph Refinement

The graph refinement part of the algorithm rebuild the complex original graph from the coarsed and simplified ones. With this idea, we can visualize complex graphs by recursively extracting its backbone structure, visualizing the simplified one, and putting the flesh back to the original graph.

# My Journey of Graph Visualization

Ah. It's indeed a very long journey. The start of the journey is that I want to visualize the structure of a small finger-tip game, and I search and read the paper of Dr. Hu. The graph visualization algorithm might sound simple. Dr. Hu's paper is very clear and direct. The difficult part, in my understanding, is how I should organize the project, design various interfaces, make visualizations during the process, and finally present the visualized work in various forms, including laser crystal curving and web 3D rendering.

In the fall of 2019, I started to think about the Graph Layout algorithm. At first, I implemented the algorithm in Python. I remember I used a list to mimic the behavior of the heap memory because I had just learned the idea of pointing to the next free space via the English Cambridge A-Level Computer Science Curriculum. Although I had zero knowledge of project structure, detailed importing practices, etc. I indeed managed to make some very interesting visualizations of the Graph Layout algorithm and Barnes-Hut tree. The visualization practices at the time are also some what problematic and not sustainable. I was just inserting codes to make PNGs of the state of the algorithms. I'm now planning to store more intermediate data and then render those information into visualizations.

At the time of 2021, when I went to college, the focus of graph visualization shifted from the algorithm to how to present the result. I took a bunch of Coursera courses on web development. The first framework I touched on was Angular. After that, by the summer of 2022, with the information I searched on the web, I learned a bit about how to draw Meshes with ThreeJS, which is enough for presenting networks. A big problem for me at the time was the Single-Canvas Multi Scene problem. The WebGL only allows me to create a few, like eight, individual canvas elements to render 3D scenes. Following the instructions from the ThreeJS official site, I could finally use a single root canvas that fills the entire viewport to render different scenes on "virtual" canvases separately.

During the winter of 2023, I took Bruno Simon's Three.js journey course to get a more comprehensive understanding of making 3D things on web. Especially how should I alter the internal data structure to change the render of the meshes, cause my ultimate goal would be to make a interactive game visualization. And finally, around the April of 2023, I managed to make a interative game visualization.

# Story Continues

There are so many visualizations to make.

---
description: "This page describes Zhifeng's Graph Visualization project."
long_title: "My Graph Visualization Project - Zhifeng"
---

# Graph Layout

The graph drawing problem is about, in my understanding, given the connections between nodes, how to assign each node a physical position such that their physical distances reflect their "in graph" distances.

```json#graph
{
    "load": ["/src/assets/jagmesh1.20240531.graph.json"]
}
```

# What did I do

- Replicated the result of Yifan Hu's paper "Efficient, high-quality force-directed graph drawing," using my own codes. My implementation includes four parts:

  1. Graph Coarsening,
  2. Force-directed Layout,
  3. Graph Refinement,
  4. Barnes-Hut tree.

- Changed and filled a few implementation and design details. Hopefully, those are improvements.

- Learned a bunch of web technologies, including HTML, CSS, and JavaScript, to render the 3D graph visualization results on webpages.

# Timeline

- **June 2024**: I implemented my Barnes-Hut Tree in Rust and published a "crate".

- **October 2023**: I began to refactor the algorithm in Rust-Lang.

- **August 2023**: I remake my personal website with React.js to display the graph visualizations.

- **June 2023**: I began to refactor the whole project in C++.

- **December 2022**: I took Bruno Simons' Three.js Journey course.

- **January 2021**: I started to think about displaying web visualization results. I found the three.js library and used it to display graphs without learning it in detail. At that time, I was developing my website in Angular. One interesting problem I solved based on the directions on the three.js official website was the "multi-scene one canvas" design.

- **November 2019**: I started to think about and implement the algorithm in Python. I have made many video visualizations of the graph visualization process. I create those visualizations by inserting PNG saving codes into the process. That's the only way I can gain helpful information for debugging. I say it's a miracle that I got the Python Barnes-hut tree to work somehow. Thinking back, I guess that's really a big monolithic project.

# Idea

The idea of the graph layout is fairly simple: we recursively extract the backbone structure of a graph until it is simple enough, visualize the simplest version, recursively put the graph "flesh" back, and tune the position of nodes accordingly during the process.

In addition to that, how to design the graph storage file for the web and, locally, for a natural experience of managing the results of different programming languages is also an interesting problem to think about.

## Graph Representation

We need to think about a graph representation that is natural and easy for web, Three.js 3D display, and local calculations.

## Graph Coarsening: Maximum Independent Vertex Set

How to get the backbone of a graph that generally preserves the original imaginary positions of nodes can be important. I guess selecting vertices with less degree can be helpful to get the outer boundary "framework" of the original graph.

## Graph Refinement

How to put the original graph's fresh back onto the backbone of visualized coarsed graph is an interesting problem to think about. Sometimes, multiple vertices of the same set of neighbors might to put into the same position, causing numerical issue of zero division.

## Barnes-Hut Tree

This is a very interesting data structure that accelerates the N-body force calculation. To some extent, the tree is an intriguing bridge between areas of numeric calculations and data structures. In general, for a node, the mass point, the tree tries to treat a large group of relatively far away nodes as one single super node. In this way, we no longer need to loop through all the other nodes and calculate forces. In the visualization below, we can see how nodes in a single cell are treated as a supernode. And the supernode becomes small when its nodes are close to the target node.

```json#graph
{
    "load": ["/src/assets/bht/Airfoil1.bht.test.json"],
    "camera_param": {
        "z": 4
    }
}
```
